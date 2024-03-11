
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Multi-master Postgres runs by default in a sandbox & nicely on virtual machines (VM's), containers or metal.  Peruse our [Change Log](CHANGELOG.md) for a complete list of incremental improvements and fixes.

Learn more [about](https://pgedge.com/company) our sponsor or try our free cloud [Developer Edition](https://www.pgedge.com/get-started/cloud) to setup a global managed cluster in less than 90 seconds.  Also check out our [Docker](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) or [K8's Helm](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) examples.  


## To install pgEdge on a single node
<details>
<summary>Node Pre-Reqs</summary>

- Use a  non-root user from the command line
- Tested with Python 3.9+ 
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.12 on OSX arm64 (experimental)
  - Python 3.12 on Fedora 39 (experimental)

- optional: config [password-less sudo](http://lussier.io/index.php/2023/04/07/passwordless-sudo/) if you want to autostart components with systemctl
- optional config [password-less ssh](http://lussier.io/index.php/2023/06/07/passwordless-ssh-to-localhost-2) to localhost for using `localhost cluster` commands
</details>

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
cd pgedge
./pgedge setup -U usr -P passwd -d demo --pg 16
```

## Cluster Tutorials using [VM's](tutorials/vm-cluster.md) or [Localhost](tutorials/localhost-cluster.md)


## Featured open source Extensions

#####  <img src=img/spock.png height=35> **[pgedge/spock](https://github.com/pgedge/spock)** - Multi-Master w/ Conflict Resolution, Auto DDL and Delta Apply

##### <img src=img/snowflake.png height=35> **[pgedge/snowflake](https://github.com/pgedge/snowflake-sequences)** - Sequences that are as unique as snowflakes

##### <img src=img/pg-community.png height=35> **[Community Extensions](supported-extensions.md)** - All the best such as Postgis, pgVector, Citus... 

## CLI Commands

<img src=img/spock-cli.png width=30>&nbsp;&nbsp; **[spock](cli/SPOCK.md)** - Commands for configuring the world's best multi-master [PostgreSQL](https://postgresql.org) extension

<img src=img/localhost.png width=30>&nbsp;&nbsp; **[localhost](cli/LOCALHOST.md)** - Create a localhost test cluster

<img src=img/vm.png width=30>&nbsp;&nbsp; **[vm](cli/VM.md)** -Provision VM's to run pgEdge (presently supports Equinix, Akamai & AWS)

<img src=img/cluster.png width=30>&nbsp;&nbsp; **[cluster](cli/CLUSTER.md)** - Define & control a cluster of VM's

<img src=img/ace.png width=30>&nbsp;&nbsp; **[ace](cli/ACE.md)** - The Anti-Chaos Engine efficiently proves your remote tables are in sync

<img src=img/db-pg.png width=30>&nbsp;&nbsp; **[db](cli/DB.md)** - Configure and control postgres db's

<img src=img/um.png width=30>&nbsp;&nbsp; **[um](cli/UM.md)** - Update manager commands

<img src=img/service.png width=25>&nbsp;&nbsp; **[service](cli/SERVICE.md)** - Service control commands

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
./pgedge cluster localhost-create cl1 2 : cluster app-install cl1 northwind
```

##### Create virtual machine (node) *n1* on **AWS** in Northen Virginia and *n2* on **Equinix Metal** in Dallas
```
./pgedge vm node-create aws iad n1 : vm node-create eqnx dfw n2
```

##### Create a multi-cloud cluster *mach1*
```
./pgedge vm cluster-create mach1 "aws:iad:n1, eqnx:dfw:n2"
```
