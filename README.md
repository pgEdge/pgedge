
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Postgres runs by default in a sandbox & nicely on virtual machines (VM's), containers or metal.  Take a look at the [community extensions](supported-extensions.md) we support or peruse our [changelog](changelog.md) for a complete list of incremental improvements and fixes.

Learn more [about](https://pgedge.com/company) our sponsor or try our free cloud [developer edition](https://www.pgedge.com/get-started/cloud) to setup a global managed cluster in less than 90 seconds.  Also check out our [containers](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) or [k8](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) examples.  


### To install [pgEdge multi-master](pgedge-extensions.md) Postgres on a single node

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
cd pgedge
./pgedge setup -U usr -P passwd -d demo --pg 16
```
Our multi-master Postgres features our **[spock](https://github.com/pgEdge/spock)** extension & **[snowflake](https://github.com/pgedge/snowflake-sequences)** sequences. 

### Easily get started
Our minimal [pre-req's](pre-reqs.md) allow you to quickly get started with [VM's](example-vm-cluster.md) or a [localhost](example-localhost-cluster.md) test cluster. 

```
./pgedge --help
```
Img | Command | Description
--- | ------- | -----------
<img src=img/spock.png width=25> | **[spock](https://github.com/pgEdge/cli/blob/REL24_1/cli/SPOCK-README.md)** | Commands for configuring the world's best multi-master [Postgres](https://postgresql.org) extension
<img src=img/localhost.png width=25>  | **[localhost](https://github.com/pgEdge/cli/blob/REL24_1/cli/LOCALHOST-README.md)** | Create a localhost test cluster
<img src=img/vm.png width=25> | **[vm](https://github.com/pgEdge/cli/blob/REL24_1/cli/VM-README.md)** | Provision VM's to run pgEdge (presently supports Equinix, Akamai & AWS)
<img src=img/cluster.png width=22> | **[cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLUSTER-README.md)** | Define & control a cluster of VM's
<img src=img/ace.png width=27> | **[ace](https://github.com/pgEdge/cli/blob/REL24_1/cli/ACE-README.md)** | The Anti-Chaos Engine helps to efficiently prove your remote tables are in sync
<img src=img/db-pg.png width=25> | **[db](https://github.com/pgEdge/cli/blob/REL24_1/cli/DB-README.md)** | Configure and control postgres db's
<img src=img/um.png width=25> | **[um](https://github.com/pgEdge/cli/blob/REL24_1/cli/UM-README.md)** | Update manager commands
<img src=img/service.png width=22> | **[service](https://github.com/pgEdge/cli/blob/REL24_1/cli/SERVICE-README.md)** | Service control commands

<details>
<summary>More CLI Examples</summary>
<br>
Sandbox with latest *Postgres 16*, *Spock* & *Snowflake* installed into default *postgres* db<br>
```
./pgedge install pg16 --start : install spock : install snowflake
```

Create db *db1* owned by *denis* installing & configuring *pgedge* core components (*Spock* & *Snowflake*) into *pg16*<br>
```
./pgedge setup -U denis -P secret -d db1 --pg 16
```

Create a cluster *cl1* on localhost with two nodes, then install *northwind sample app* on *cl1* cluster<br>
```
./pgedge cluster localhost-create cl1 2 : cluster app-install cl1 northwind<br>
```

Create virtual machine (node) *n1* on **AWS** in Northen Virginia and *n2* on **Equinix Metal** in Dallas<br>
```
./pgedge vm node-create aws iad n1 : multicloud node-create eqnx dfw n2<br>
```

Create a multi-cloud cluster *mach1*<br>
```
./pgedge vm cluster-create mach1 "aws:iad:n1, eqnx:dfw:n2"
```
</details>
