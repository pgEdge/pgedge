# PGEDGE CLOUD
Secure CLI Interface to pgEdge Cloud

## Synopsis
    ./ctl cloud  <command> [parameters] [options]   

[**config**](doc/cloud-config.md)                         - Login with a pgEdge Cloud Account<br>
[**list-linked-accts**](doc/cloud-list-linked-accts.md)   - List all cloud account ids in a pgEdge Cloud Account<br>
[**list-clusters**](doc/cloud-list-clusters.md)           - List all clusters in a pgEdge Cloud Account<br>
[**cluster-status**](doc/cloud-cluster-status.md)         - Return info on a cluster in a pgEdge Cloud Account<br>
[**list-nodes**](doc/cloud-list-nodes.md)                 - List all nodes in a pgEdge Cloud Account cluster<br>
[**import-cluster-def**](doc/cloud-import-cluster-def.md) - Enable cluster commands on a pgEdge Cloud Cluster<br>
[**get-cluster-id**](doc/cloud-get-cluster-id.md)         - Return the cluster id based on a cluster display name<br>
[**get-node-id**](doc/cloud-get-node-id.md)               - Return the node id based on cluster and node display name<br>
[**push-metrics**](doc/cloud-push-metrics.md)             - Coming Soon: push pgEdge Metrics to a specified target<br>
[**create-cluster**](doc/cloud-create-cluster.md)         - Create a new Cloud Cluster based on json file<br>
[**destroy-cluster**](doc/cloud-destroy-cluster.md)       - Delete a pgEdge Cloud Cluster<br>

## Options
    --json             # Turn on JSON output
    --debug            # Turn on debug logging
    --silent           # Less noisy
    --verbose or -v    # More noisy

