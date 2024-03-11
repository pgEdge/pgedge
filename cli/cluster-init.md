## SYNOPSIS
    ./pgedge cluster init CLUSTER_NAME
 
## DESCRIPTION
    Install pgedge on each node, create the initial database, install spock, and create all spock nodes and subscriptions. 
Additional databases will be created with all spock nodes and subscriptions if defined in the json file.
This command requires a JSON file with the same name as the cluster to be in the cluster/<cluster_name>. 

Example: cluster init demo 
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
