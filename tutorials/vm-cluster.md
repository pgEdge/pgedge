# pgEdge Platform - Getting Started Guide

In this tutorial we will step through setting up pgEdge on VM's. Our example will create a two-node multi-master pgEdge cluster, and then use pgbench to create some representative tables and read/write activity on the cluster.


Before running the commands ensure that a firewall doesn't obstruct access between your nodes. You’ll also need an operating system user with with passwordless sudo access.

## Prerequisites
- EL8 or EL9 (RHEL/CentOS/Rocky), or Ubuntu-22.04
- Rocky Linux 9 recommend. For AWS users, easily find the [ami here](https://rockylinux.org/cloud-images/)
- A non-root user with passwordless `sudo` privileges
- Two servers (vm's are fine) networked with traffic on port 5432 allowed
- Passwordless SSH access into both servers via the non-root user above

## Installation
In any directory owned by your non-root user, invoke the following command to create the pgedge directory and install `ctl`:
<pre>
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
</pre>

cd into the `pgedge` directory and setup ***pgEdge*** with the `pgedge setup` command. 
Specify a name for the database superuser name, password, and a database name. 
Note that the name cannot be the name of an OS superuser, pgEdge, or any of the Postgres reserved words. 

<pre>
cd pgedge
./pgedge setup -U superuser-name -P superuser-password -d database-name
</pre>

For the examples that follow, I'll invoke the `pgedge setup` command with options that install Postgres with database named `demo`, owned by a database superuser named `admin`, with a password of `mypassword1`. Use the following command to create those database objects:

<pre>
./pgedge setup -U admin -P mypassword1 -d demo
</pre>

If you encounter a permissions error on EL9 running this command, you may need to update your SELINUX mode to `permissive` or `disabled`, reboot, and retry the operation.

## Configuration 
Using `pgedge` CLI on each node, create the spock components needed for replication. First you will create a spock node by providing a name for the node and a connection string that includes the network address, the name of an OS user with root privileges (in our example, `pgedge`), and the database name (`demo`). The connection string is also followed by the database name.

Next you will create a replication set by providing the replication set name and the database name. The node name (n1) and the replication set name (demo_replication_set) can be set to any valid value you choose, but you will have to reference them in future commands.

Node `n1` (IP address 10.1.2.5):
<pre>
./pgedge spock node-create n1 'host=10.1.2.5 user=pgedge dbname=demo' demo
./pgedge spock repset-create demo_replication_set demo
</pre>

Node `n2` (IP address 10.2.2.5):
<pre>
./pgedge spock node-create n2 'host=10.2.2.5 user=pgedge dbname=demo' demo
./pgedge spock repset-create demo_replication_set demo
</pre>

Next, use ctl to create the subscriptions. For these commands you will provide a unique subscription name for each node, followed by a connection string that specifies the network address for the other node in the subscription (the node that the current node is subscribing to), the port that will handle database connections for the set, the name of the replication set owner, and the database name. Again, the command is followed by the name of the database.

On node `n1`:
<pre>
./pgedge spock sub-create sub_n1n2 'host=10.2.2.5 port=5432 user=pgedge dbname=demo' demo
</pre>

On node `n2`:
<pre>
./pgedge spock sub-create sub_n2n1 'host=10.1.2.5 port=5432 user=pgedge dbname=demo' demo
</pre>

## Creating tables and customizing replication rules

At this point, you will have a two node cluster with cross subscriptions that connect `n1` to `n2` and `n2` to `n1`. For replication to begin, you will need to add tables to the replication sets, and then add those replication sets to the subscriptions. To simplify performing the commands that follow, you may want to open a second terminal window so you can have windows open for both operating system access/pgbench and psql. When you open pgbench or psql, specify your database name after the utility name.

On each node, source the Postgres environment variables to simplify using database tools with the following command:
<pre>
source pg15/pg15.env
</pre>

This adds the Postgres pgbench and psql utilities to your OS PATH. 

For this example, I will be using pgbench to set up a very simple four-table database. On each node of your replication set, initialize a PostgreSQL database with the pgbench command. This will result in all nodes containing the same schema and data:
<pre>
pgbench -i demo
</pre>

Then, connect to each node with the psql client:

<pre>
psql demo
</pre>

Once connected, alter the numeric columns, setting `LOG_OLD_VALUE` equal to `true`.  This will make these numeric fields conflict-free delta-apply columns, ensuring that the value replicated is the delta of the committed changes (the old value plus or minus any new value) to a given record:

<pre>
ALTER TABLE pgbench_accounts ALTER COLUMN abalance SET (LOG_OLD_VALUE=true);
ALTER TABLE pgbench_branches ALTER COLUMN bbalance SET (LOG_OLD_VALUE=true);
ALTER TABLE pgbench_tellers ALTER COLUMN tbalance SET (LOG_OLD_VALUE=true);
</pre>

 Then, on the OS command line for each node, run the following command on both nodes to add these tables to the replication set. The fourth table, pgbench_history, will not be added because it does not have a primary key.
<pre>
./pgedge spock repset-add-table demo_replication_set 'pgbench_*' demo
</pre>

On the OS command line, finish the set up by adding the replication sets to the subscriptions you had created.<br>

On node `n1`:
<pre>
./pgedge spock sub-add-repset sub_n1n2 demo_replication_set demo
</pre>

On node `n2`:
<pre>
./pgedge spock sub-add-repset sub_n2n1 demo_replication_set demo
</pre>

On the psql command line, check the configuration with the following SQL statements:
<pre>
demo=# SELECT * FROM spock.node;
node_id | node_name
---------+----------
673694252 | n1
560818415 | n2
(2 rows)
</pre>
<pre>
demo=# SELECT sub_id, sub_name, sub_slot_name, sub_replication_sets  FROM spock.subscription;
   sub_id   | sub_name |	sub_slot_name 	|                	sub_replication_sets             
------------+----------+----------------------+--------------------------------------------------------
 3293941396 | sub_n1n2 | spk_demo_n2_sub_n1n2 | {default,default_insert_only,ddl_sql,demo_replication_set}
(1 row)
</pre>

## Testing Replication
Now, if you update a row on `n1`, you should see the update to the same row on `n2`.

On `n1`:
<pre>
demo=# SELECT * FROM pgbench_tellers WHERE tid = 1;
 tid | bid | tbalance | filler
-----+-----+----------+--------
   1 |   1 |    	0 |
 (1 row)
</pre>

<pre>
demo=# UPDATE pgbench_tellers SET filler = 'test' WHERE tid = 1;
UPDATE 1
</pre>

Check `n2`:
<pre>
demo=# SELECT * FROM pgbench_tellers WHERE tid = 1;
 tid | bid | tbalance | filler  	 
-----+-----+----------+--------------------------------------------------
   1 |   1 |    	0 | test                               
(1 row)
</pre>

You can also use pgbench to exercise replication; run the following command on both nodes at the same time to run pgbench for one minute. 
<pre>
pgbench -R 100 -T 60 -n demo
</pre>

When you check the results on both nodes, you'll see that the sum of the tbalance columns match on both pgbench_tellers tables. Without the conflict-free delta-apply columns, each conflict would have resulted in accepting the first in, potentially leading to sums that do not match between nodes.
 
`n1`:
<pre>
demo=# SELECT SUM(tbalance) FROM pgbench_tellers;
  sum  |
 ------+
 -84803
(1 row)
</pre>

`n2`:
<pre>
demo=# SELECT SUM(tbalance) FROM pgbench_tellers;
  sum  |
 ------+
 -84803
(1 row)
</pre>

