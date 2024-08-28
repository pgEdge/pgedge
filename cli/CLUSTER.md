# CLI for Cluster control
Installation and configuration of a pgEdge SPOCK cluster

## Synopsis
    ./pgedge cluster <command> [parameters]
[**json-validate**](help/cluster-json-validate.md)        - Validate a Cluster Configuration JSON file<br>
[**json-template**](help/cluster-json-template.md)        - Create a template for a Cluster Configuration JSON file<br>
[**init**](help/cluster-init.md)     - Initialize a cluster via Cluster Configuration JSON file<br>
[**list-nodes**](help/cluster-list-nodes.md)	- List all nodes in the cluster.<br>
[**add-node**](help/cluster-add-node.md)	- Adds a new node to a cluster, copying configurations from a specified source node.<br>
[**remove-node**](help/cluster-remove-node.md)	- Remove a node from the cluster configuration.<br>
[**replication-begin**](help/cluster-replication-begin.md)     - Add all tables to replication on every node<br>
[**replication-check**](help/cluster-replication-check.md)     - Show replication status on every node<br>
[**remove**](help/cluster-remove.md)   - Remove a test cluster<br>
[**command**](help/cluster-command.md)             - Run a CLI command on one or all nodes of a cluster<br>
[**ssh**](help/cluster-ssh.md)	-An SSH Terminal session into the specified node.<br>
[**app-install**](help/cluster-app-install.md)     - Install an application such as NorthWind or pgBench<br>
[**app-remove**](help/cluster-app-remove.md)       - Remove an applicatio.<br>
