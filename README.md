
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Postgres runs by default in a sandbox & nicely on vm's, containers or metal.  Take a look at the community [extensions](supported-extensions.md) we support or peruse our [changes](changelog.md) for a complete list of current improvements and fixes.

Our free [cloud](https://www.pgedge.com/get-started/cloud) developer edition lets you setup a global managed cluster in less than 90 seconds.  Also check out our [containers](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) or [k8](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) examples.


## To install our latest stable open source binaries from CLI:

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```
<details>
<summary>CLI Pre Req's</summary>

- Install as a non-root user from your `$HOME` directory

- configure [password-less sudo](http://lussier.io/index.php/2023/04/07/passwordless-sudo/) and [password-less ssh to localhost](http://lussier.io/index.php/2023/06/07/passwordless-ssh-to-localhost-2) for using `localhost cluster` commands

- Tested with Python 3.9+ 
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.12 on OSX arm64 (experimental)
  - Python 3.12 on Fedora 39 (experimental)

Get started with a cluster of [VM's](getting-started.md) or a [localhost]() cluster. 
</details>

<details>
<summary>CLI Documentation</summary>

- [spock](https://github.com/pgEdge/cli/blob/REL24_1/cli/SPOCK-README.md) - Multi-master Postgres configuration
- [cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLUSTER-README.md) - Create and control a remote cluster
- [localhost](https://github.com/pgEdge/cli/blob/REL24_1/cli/LOCALHOST-README.md) - Create a localhost cluster
- [vm](https://github.com/pgEdge/cli/blob/REL24_1/cli/VM-README.md) - Provision virtual machines (supports Equinix, Akamai & AWS)
- [ace](https://github.com/pgEdge/cli/blob/REL24_1/cli/ACE-README.md) - The **A**nti **C**haos **E**ngine helps to efficiently prove your remote tables are in sync
- [db](https://github.com/pgEdge/cli/blob/REL24_1/cli/DB-README.md) - Configure and control Postgres db's
- [um](https://github.com/pgEdge/cli/blob/REL24_1/cli/UM-README.md) - Update Manager commands
- [service](https://github.com/pgEdge/cli/blob/REL24_1/cli/SERVICE-README.md) - Service control commands
</details>

<details>
<summary>Usage Samples</summary>
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

Authenticate with pgEdge Cloud credentials, then list your clusters<br>
```
./pgedge cloud login : cloud cluster-list
```

Create virtual machine (node) *n1* on **AWS** in Northen Virginia and *n2* on **Equinix Metal** in Dallas<br>
```
./pgedge multicloud node-create aws iad n1 : multicloud node-create eqnx dfw n2<br>
```

Create a multi-cloud cluster *mach1*<br>
```
./pgedge multicloud cluster-create mach1 "aws:iad:n1, eqnx:dfw:n2"
```
</details>
