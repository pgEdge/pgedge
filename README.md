
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Multi-master Postgres runs nicely (on most all flavors of Linux) in vm's, containers, bare metal, or a localhost sandbox.  

You can join our [Discord Server](https://discord.com/invite/QaqHy52sUd) or learn more about [our sponsor](https://pgedge.com/company).
Try our free [Cloud Developer Edition](https://www.pgedge.com/get-started/cloud) to setup a global managed cluster in less than 90 seconds.  Also check out our [Docker](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) or [K8's Helm](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) examples.  


##  Getting started 
Start by installling CLI on a single node (as per above) and then looking next at quick tutorial.

<details>
<summary>Node Pre-Reqs</summary>

- Use a  non-root user from the command line
- Tested with Python 3.9 thru 3.12
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.11 on Debian 12
  - *Experimental* on Python 3.12 on Ubuntu 24.04 & Fedora 40

- optional: config [password-less sudo](http://lussier.io/index.php/2023/04/07/passwordless-sudo/) if you want to autostart components with systemctl
- optional config [password-less ssh](http://lussier.io/index.php/2023/06/07/passwordless-ssh-to-localhost-2) to localhost for using `localhost cluster` commands
</details>

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```

## Try a cluster tutorial using [localhost](cli/tutorials/localhost-cluster.md) or [vm's](cli/tutorials/vm-cluster.md).

## Learn more about our family of [supported components](supported-components.md)

## Get a feel for our powerful CLI commands

##### <img src=img/spock-cli.png width=30>&nbsp;&nbsp; **[spock](cli/SPOCK.md)** - Custom configure world's best logical & multi-master distributed Postgres

##### <img src=img/localhost.png width=30>&nbsp;&nbsp; **[localhost](cli/LOCALHOST.md)** - Create a localhost test cluster

##### <img src=img/cluster.png width=30>&nbsp;&nbsp; **[cluster](cli/CLUSTER.md)** - Define & control a cluster of nodes

##### <img src=img/ace.png width=30>&nbsp;&nbsp; **[ace](cli/ACE.md)** - The Anti-Chaos Engine efficiently assures your distributed data is in sync

##### <img src=img/db-pg.png width=30>&nbsp;&nbsp; **[db](cli/DB.md)** - Configure and control distributed PostgreSQL DB's

##### <img src=img/um.png width=30>&nbsp;&nbsp; **[um](cli/UM.md)** - Update Manager commands

##### <img src=img/service.png width=25>&nbsp;&nbsp; **[service](cli/SERVICE.md)** - Service control commands

## CLI Examples
##### Sandbox with latest *Postgres 16*, *Spock* & *Snowflake* installed into default *postgres* db
```
./pgedge install pg16 --start : install spock : install snowflake
```

##### Create database *db1* owned by *denis* & setting up *Spock* & *Snowflake*  into *pg16*
```
./pgedge setup -U denis -P secret -d db1 --pg_ver 16
```

##### Create a cluster *cl1* on localhost with two nodes, then install *northwind sample app* on cluster
```
./pgedge localhost cluster-create cl1 2 : cluster app-install cl1 northwind
```
