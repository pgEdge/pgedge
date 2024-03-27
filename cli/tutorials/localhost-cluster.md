# Creating a Localhost Cluster


## Prerequisites
- [Install the CLI](https://github.com/pgEdge/pgedge/tree/main?tab=readme-ov-file#getting-started) and make sure you look at the pre-reqs there & get both `password-less ssh` and `passwordless sudo` to localhost working first.


## Create a localhost pgEdge cluster with spock and snowflake on each node
<pre>
./pgedge localhost cluster-create --name cl1 --nodes 2  --port1 6432
</pre>

The above command creates the `cl1` localhost 2 node cluster with node `n1` on port 6432 and `n2` on port 6433.

## Install the sample Northwind app and configure it for Spock multi-master replication between nodes
You can install the Northwind database on this localhost cluster with the following command:
<pre>
./pgedge cluster app-install cl1 northwind
</pre>

## Use ACE to ensure tables are in sync
<pre>
./pgedge ace table-diff cl1 northwind.accounts
</pre>


