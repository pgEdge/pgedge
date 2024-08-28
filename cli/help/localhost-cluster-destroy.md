## SYNOPSIS
    ./pgedge localhost cluster-destroy CLUSTER_NAME
 
## DESCRIPTION
    Destroy a local cluster. This will stop postgres on each node, and then remove
the pgedge directory for each node in a local cluster.
Example: localhost cluster-destroy demo
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
