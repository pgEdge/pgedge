## SYNOPSIS
    ./pgedge cluster add-node CLUSTER_NAME SOURCE_NODE TARGET_NODE <flags>
 
## DESCRIPTION
    Adds a new node to a cluster, copying configurations from a specified source node.
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster to which the node is being added.
    SOURCE_NODE
        The node from which configurations are copied.
    TARGET_NODE
        The new node.
 
## FLAGS
    -r, --repo1_path=REPO1_PATH
        The repo1 path to use.
    
    -b, --backup_id=BACKUP_ID
        Backup ID.
    
    --script=SCRIPT
        Bash script.
    
    --stanza=STANZA
        Stanza name.
    
