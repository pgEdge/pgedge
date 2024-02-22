
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Postgres runs nicely on bare metal, vm's, & containers, but...  perhaps you are asking yourself, "[What is pgEdge?](https://www.pgedge.com/products/what-is-pgedge)"

# For free trial versions of production ready software:
- Try [pgEdge Platform](https://www.pgedge.com/get-started/platform) to host and manage a pgEdge cluster yourself or [Cloud Developer Edition](https://www.pgedge.com/get-started/cloud) and be running a global managed cluster in < 90s (and get a free t-shirt)

# To install our latest developers CLI & binaries:

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```

<details>
<summary>Getting Started</summary>

- [2 node cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/GETTING-STARTED.md) on self provisioned VM's or bare-metal
- [Container](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) strategy and examples
</details>

<details>
<summary>CLI Documentation</summary>

- [spock](https://github.com/pgEdge/cli/blob/REL24_1/cli/SPOCK-README.md) - Multi-Master Postgres node configuration
- [cloud](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLOUD-README.md) - Secure control you pgEdge Cloud clusters
- [cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLUSTER-README.md) - Create and control a local cluster
- [multicloud](https://github.com/pgEdge/cli/blob/REL24_1/cli/MULTICLOUD-README.md) - for rapidly assembling Multicloud test clusters
- [ace](https://github.com/pgEdge/cli/blob/REL24_1/cli/ACE-README.md) - The **A**nti **C**haos **E**ngine helps to efficiently prove your remote tables are in sync
- [db](https://github.com/pgEdge/cli/blob/REL24_1/cli/DB-README.md) - Configure and control Postgres db
- [um](https://github.com/pgEdge/cli/blob/REL24_1/cli/UM-README.md) - Update Manager commands
- [service](https://github.com/pgEdge/cli/blob/REL24_1/cli/SERVICE-README.md) - Service control commands
</details>


<details>
<summary>Useful Notes</summary>

- Interested in our [CHANGELOG](https://github.com/pgEdge/cli/blob/REL24_1/CHANGELOG.md)

- Install as a non-root user from your `$HOME` directory

- configure [password-less sudo](http://lussier.io/index.php/2023/04/07/passwordless-sudo/) for easier testing of advanced commands

- set up [password-less ssh to localhost](http://lussier.io/index.php/2023/06/07/passwordless-ssh-to-localhost-2) for using `cluster localhost-create` commands

- Tested with Python 3.9+ 
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.11 on Ubuntu 23.10 (experimental)
  - Python 3.12 on Fedora 39 (experimental)

- pgEdge [Community License](https://www.pgedge.com/communitylicense)
</details>


<details>
<summary>Usage Samples</summary>

Sandbox with latest *Postgres 16*, *Spock* & *Snowflake* installed into default *postgres* db<br>
```
./pgedge install pg16 --start : install spock : install snowflake
```

Create db *db1* owned by *denis* installing & configuring *pgedge* core components (*Spock* & *Snowflake*) into *pg16*

```
./pgedge install pgedge -U denis -P secret -d db1 --pg 16
```


Create a cluster *cl1* on localhost with two nodes, then install *northwind sample app* on *cl1* cluster

```
./pgedge cluster localhost-create cl1 2 : cluster app-install cl1 northwind
```

Create cluster *clc* in docker compose with three nodes (**Coming Soon!**)
```
./pgedge cluster container-create clc 3 : cluster app-install clc pgbench
```

Authenticate with pgEdge Cloud credentials, then list your clusters
```
./pgedge cloud login : cloud cluster-list
```

Create virtual machine *n1* on **AWS** in Northen Virginia and virtual machine *n2* on **Equinix Metal** in Dallas
```
./pgedge multicloud node-create aws iad n1 : multicloud node-create eqnx dfw n2
```

Create a multi-cloud cluster *mach1* (**Coming Soon!**)
```
./pgedge multicloud cluster-create mach1 "aws:iad:n1, eqnx:dfw:n2"
```
</details>
