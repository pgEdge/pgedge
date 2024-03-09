
![# pgEdge Distributed Postgres](img/pgedge-dp-banner.png)

Our Distributed Postgres runs by default in a sandbox & nicely on vm's, containers or metal.  Take a look at the community [extensions](supported-extensions.md) we support or peruse our [changes](changelog.md) for a complete list of current improvements and fixes.

Our free [cloud](https://www.pgedge.com/get-started/cloud) developer edition lets you setup a global managed cluster in less than 90 seconds.  Also check out our [containers](https://github.com/pgEdge/pgedge-docker/blob/main/README.md) or [k8](https://github.com/pgEdge/pgedge-helm/blob/main/examples/README.md) examples.  

Learn more about [our sponsor](https://pgedge.com).


### To install our open source binaries

```
python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install.py)"
```
### Easily get started
Our minimal [pre-req's]() allow you to quickly get started with an example [VM](example-vm-cluster.md) or [localhost](example-localhost-cluster.md) cluster. 

### CLI Help
- [setup]() - A postgres node running pgEdge (includes ***[spock]()*** & ***[snowflake]()*** extensions)<br>
- [spock](https://github.com/pgEdge/cli/blob/REL24_1/cli/SPOCK-README.md) - The CLI for the world's best multi-master [Postgres](https://postgresql.org) extension
- [localhost](https://github.com/pgEdge/cli/blob/REL24_1/cli/LOCALHOST-README.md) - Create a localhost cluster
- [vm](https://github.com/pgEdge/cli/blob/REL24_1/cli/VM-README.md) - Provision VM's to run pgEdge (presently supports Equinix, Akamai & AWS)
- [cluster](https://github.com/pgEdge/cli/blob/REL24_1/cli/CLUSTER-README.md) - Define & control a cluster of VM's
- [ACE](https://github.com/pgEdge/cli/blob/REL24_1/cli/ACE-README.md) - The Anti-Chaos Engine helps to efficiently prove your remote tables are in sync
- [db](https://github.com/pgEdge/cli/blob/REL24_1/cli/DB-README.md) - Configure and control Postgres db's
<br><br>
- [um](https://github.com/pgEdge/cli/blob/REL24_1/cli/UM-README.md) - Update Manager commands
- [service](https://github.com/pgEdge/cli/blob/REL24_1/cli/SERVICE-README.md) - Service control commands

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
