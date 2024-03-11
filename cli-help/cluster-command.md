## SYNOPSIS
    ./pgedge cluster command CLUSTER_NAME NODE CMD <flags>
 
## DESCRIPTION
    Run './pgedge' commands on one or all of the nodes in a cluster. 
This command requires a JSON file with the same name as the cluster to be in the cluster/<cluster_name>. 

Example: cluster command demo n1 status
Example: cluster command demo all spock repset-add-table default * lcdb
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
    NODE
        The node to run the command on. Can be the node name or all.
    CMD
        The command to run on every node, excluding the beginning ./pgedge
 
## FLAGS
    -a, --args=ARGS
    
    
