# Creating a Localhost Cluster


## Prerequisites
- Install the CLI and make sure you get `password-less ssh to localhost` and passwordless sudo to localhost host working first.


## Installation
<pre>
cd pgedge
./pgedge localhost cluster-create --help
./pgedge localhost cluster-create --name cl1 --nodes 2  --port1 6432
</pre>

The above command creates the `cl1` localhost 2 node cluster with node `n1` on port 6432 and `n2` on port 6433.

## Try it with some sample data
You can install the Northwind database on this localhist cluster with the following command:
<pre>
./pgedge cluster app-install cl1 northwind
</pre>
