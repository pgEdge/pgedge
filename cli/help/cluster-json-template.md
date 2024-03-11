## SYNOPSIS
    ./pgedge cluster json-template CLUSTER_NAME DB NUM_NODES USR PASSWD PG PORT
 
## DESCRIPTION
    Create a JSON configuration file template that can be modified to fully define a remote cluster. 

Example: cluster define-remote demo lcdb 3 lcusr lcpasswd 16 5432
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster. A directory with this same name will be created in the cluster directory, and the JSON file will have the same name.
    DB
        The database name.
    NUM_NODES
        The number of nodes in the cluster.
    USR
        The username of the superuser created for this database.
    PASSWD
        The password for the above user.
    PG
        The postgres version of the database.
    PORT
