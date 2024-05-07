
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Multi-master Postgres runs by default in a sandbox & nicely on virtual machines (VM's), containers, metal or localhost sandboxes.  Peruse our [CHANGELOG](CHANGELOG.md) for a complete list of incremental improvements and fixes and, if you fancy, join our [Discord Server](https://discord.com/invite/QaqHy52sUd).

Learn more about [our sponsor](https://pgedge.com/company) or try our free cloud [Developer Edition](https://www.pgedge.com/get-started/cloud) to setup a global managed cluster in less than 90 seconds.  Also check out our [Docker](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) or [K8's Helm](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) examples.  


##  Getting started 
<details>
<summary>Node Pre-Reqs</summary>

- Use a  non-root user from the command line
- Tested with Python 3.9+ 
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.11 on OSX arm64 (experimental)
  - Python 3.12 on Ubuntu 24.04 (experimental)
  - Python 3.12 on Fedora 39 (experimental)

- optional: config [password-less sudo](http://lussier.io/index.php/2023/04/07/passwordless-sudo/) if you want to autostart components with systemctl
- optional config [password-less ssh](http://lussier.io/index.php/2023/06/07/passwordless-ssh-to-localhost-2) to localhost for using `localhost cluster` commands
</details>

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```
Start by installling CLI on a single node (as per above) and then looking next at [below examples](#cli-examples).

## Or try our **Tutorials** using <img src=img/vm.png width=20>&nbsp;[Virtual Machines](cli/tutorials/vm-cluster.md) or <img src=img/localhost.png width=25>&nbsp;[Localhost Clusters](cli/tutorials/localhost-cluster.md).


## Learn more about our featured extensions
##### <img src=img/spock.png height=30> **[spock](https://github.com/pgedge/spock)** - Multi-master w/ Conflict Resolution, Auto DDL and Delta Apply

##### <img src=img/snowflake.png height=30> **[snowflake-sequences](https://github.com/pgedge/snowflake-sequences)** - Sequences that are as unique as snowflakes

##### <img src=img/pg-community.png height=30> **[Supported Extensions](supported-extensions.md)** - All the best such as Postgis, pgVector, Citus... 

## Get a feel for our powerful CLI commands

##### <img src=img/spock-cli.png width=30>&nbsp;&nbsp; **[spock](cli/SPOCK.md)** - Custom configure world's best logical & multi-master [Postgres](https://postgresql.org) extension

##### <img src=img/localhost.png width=30>&nbsp;&nbsp; **[localhost](cli/LOCALHOST.md)** - Create a localhost test cluster

##### <img src=img/cluster.png width=30>&nbsp;&nbsp; **[cluster](cli/CLUSTER.md)** - Define & control a cluster of VM's or Metal

##### <img src=img/vm.png width=27>&nbsp;&nbsp; **[vm](cli/VM.md)** - Convenience commands to manage Virtual Machines

##### <img src=img/ace.png width=30>&nbsp;&nbsp; **[ace](cli/ACE.md)** - The Anti-Chaos Engine efficiently proves your remote tables are in sync

##### <img src=img/db-pg.png width=30>&nbsp;&nbsp; **[db](cli/DB.md)** - Configure and control postgres db's

##### <img src=img/um.png width=30>&nbsp;&nbsp; **[um](cli/UM.md)** - Update manager commands

##### <img src=img/service.png width=25>&nbsp;&nbsp; **[service](cli/SERVICE.md)** - Service control commands

## CLI Examples
##### Sandbox with latest *Postgres 16*, *Spock* & *Snowflake* installed into default *postgres* db
```
./pgedge install pg16 --start : install spock : install snowflake
```

##### Create database *db1* owned by *denis* & setting up *Spock* & *Snowflake*  into *pg16*
```
./pgedge setup -U denis -P secret -d db1 --pg 16
```

##### Create a cluster *cl1* on localhost with two nodes, then install *northwind sample app* on cluster
```
./pgedge localhost cluster-create cl1 2 : cluster app-install cl1 northwind
```

##### Create virtual machine (node) *n1* on **AWS** in Northen Virginia (iad) and *n2* on **Equinix Metal** in Dallas (dfw)
```
./pgedge vm create aws iad n1 : vm node-create eqnx dfw n2
```

##### Create a multi-cloud cluster *mach1*
```
./pgedge vm cluster-define mach1 "aws:iad:n1, eqnx:dfw:n2"
```
