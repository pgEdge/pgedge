
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

We build our enterprise-class, secure and statically linked binaries on Rocky Linux 8 & 9 for *x86_64* & and on Rocky Linux 9 for *arm64*.   Our binaries run nicely on bare metal, vm's, containers or a localhost sandbox on your laptop.  We are tested to run on EL8, EL9, SLES-15, AWS Linux 2023, and Ubuntu 22.04.

# To install Production ready release:
[pgEdge Platform Download](https://www.pgedge.com/download)

# To install our Latest 24.1.x Developers Lab CLI:

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```

[Useful Notes](#useful-notes)<br>
[Usage Samples](#usage-samples)<br>
[CLI Documentation](https://github.com/pgedge/cli/blob/REL24_1/cli/README.md)

# Useful Notes:
- Interested in our [CHANGELOG](https://github.com/pgEdge/cli/blob/REL24_1/CHANGELOG.md)

- Install as a non-root user from your `$HOME` directory

- configure [password-less sudo](https://blog.pgedge.org/index.php/2023/04/07/passwordless-sudo/) for easier testing of advanced commands

- set up [password-less ssh to localhost](https://blog.pgedge.org/index.php/2023/06/07/passwordless-ssh-to-localhost-2) for using `cluster localhost-create` commands

- Tested with Python 3.9+ 
  - Python 3.9 on EL8, EL9, SLE-15, & Amazon Linux 2023
  - Python 3.10 on Ubuntu 22.04
  - Python 3.11 on Ubuntu 23.10
  - Python 3.12 on Fedora 39

- Denis' [Linux Cheatsheet](http://lussier.io)

- pgEdge [Community License](https://www.pgedge.com/communitylicense)



# Usage Samples:

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
