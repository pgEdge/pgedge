## SYNOPSIS
    ./pgedge cluster remove CLUSTER_NAME <flags>
 
## DESCRIPTION
    Remove a cluster. This will remove spock subscriptions and nodes, and then stop postgres on each node. If the flag force is set to true, then it will also remove the pgedge directory on each node.
This command requires a JSON file with the same name as the cluster to be in the cluster/<cluster_name>. 

Example: cluster remove demo 
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
 
## FLAGS
    -f, --force=FORCE
    
    
