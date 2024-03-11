## SYNOPSIS
    ./pgedge cluster add-db CLUSTER_NAME DATABASE_NAME USERNAME PASSWORD
 
## DESCRIPTION
    Create the new database in the cluster, install spock, and create all spock nodes and subscriptions.
This command requires a JSON file with the same name as the cluster to be in the cluster/<cluster_name>. 

Example: cluster add-db demo test admin password
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the existing cluster.
    DATABASE_NAME
        The name of the new database.
    USERNAME
        The name of the user that will be created and own the db.
    PASSWORD
        The password for the new user.
