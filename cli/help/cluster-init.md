## SYNOPSIS
    ./pgedge cluster init CLUSTER_NAME
 
## DESCRIPTION
    Install pgEdge on each node, create the initial database, install Spock,
and create all Spock nodes and subscriptions. Additional databases will
be created with all Spock nodes and subscriptions if defined in the JSON
file. This command requires a JSON file with the same name as the cluster
to be in the cluster/<cluster_name>.
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
