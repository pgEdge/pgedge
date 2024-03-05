
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Postgres runs nicely on bare metal, vm's, & containers, but...  perhaps you are asking yourself, 
"What are the [supported extensions](community-extensions.md)?" or "What does the [changelog](changelog.md) look like?"

You can try our [cloud developer edition](https://www.pgedge.com/get-started/cloud) for free and be running a global managed cluster in < 90s (and get a free tshirt)

# To install our latest stable open source binaries:

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```

<details>
<summary>Getting Started</summary>

- [2 node cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/GETTING-STARTED.md) on self provisioned VM's or bare-metal
- [Container](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) strategy and docker-compose examples
- [Helm & Kubernetes](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) charts & examples
</details>

<details>
<summary>CLI Documentation</summary>

- [spock](https://github.com/pgEdge/cli/blob/REL24_1/cli/SPOCK-README.md) - Multi-master Postgres configuration
- [cloud](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLOUD-README.md) - Securely control your pgEdge Cloud clusters
- [cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLUSTER-README.md) - Create and control a localhost or remote cluster
- [vm](https://github.com/pgEdge/cli/blob/REL24_1/cli/VM-README.md) - Provision & control virtual machines on multiple clouds
- [ace](https://github.com/pgEdge/cli/blob/REL24_1/cli/ACE-README.md) - The **A**nti **C**haos **E**ngine helps to efficiently prove your remote tables are in sync
- [db](https://github.com/pgEdge/cli/blob/REL24_1/cli/DB-README.md) - Configure and control Postgres db's
- [um](https://github.com/pgEdge/cli/blob/REL24_1/cli/UM-README.md) - Update Manager commands
- [service](https://github.com/pgEdge/cli/blob/REL24_1/cli/SERVICE-README.md) - Service control commands
</details>


<details>
<summary>Useful Notes</summary>

- Install as a non-root user from your `$HOME` directory

- configure [password-less sudo](http://lussier.io/index.php/2023/04/07/passwordless-sudo/) for easier testing of advanced commands

- set up [password-less ssh to localhost](http://lussier.io/index.php/2023/06/07/passwordless-ssh-to-localhost-2) for using `cluster localhost-create` commands

- Tested with Python 3.9+ 
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.11 on Ubuntu 23.10 (experimental)
  - Python 3.11 on OSX arm64 (experimental)
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
./pgedge setup -U denis -P secret -d db1 --pg 16
```

Create a cluster *cl1* on localhost with two nodes, then install *northwind sample app* on *cl1* cluster
```
./pgedge cluster localhost-create cl1 2 : cluster app-install cl1 northwind
```

Authenticate with pgEdge Cloud credentials, then list your clusters
```
./pgedge cloud login : cloud cluster-list
```

Create virtual machine (node) *n1* on **AWS** in Northen Virginia and *n2* on **Equinix Metal** in Dallas
```
./pgedge multicloud node-create aws iad n1 : multicloud node-create eqnx dfw n2
```

Create a multi-cloud cluster *mach1*
```
./pgedge multicloud cluster-create mach1 "aws:iad:n1, eqnx:dfw:n2"
```
</details>
