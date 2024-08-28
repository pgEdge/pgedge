## SYNOPSIS
    ./pgedge cluster app-install CLUSTER_NAME APP_NAME <flags>
 
## DESCRIPTION
    Install a test application on all of the nodes in a cluster. 
This command requires a JSON file with the same name as the cluster to be in the cluster/<cluster_name>. 

Example: cluster app-install pgbench
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
    APP_NAME
        The application name, pgbench or northwind.
 
## FLAGS
    -d, --database_name=DATABASE_NAME
    
    
    -f, --factor=FACTOR
        The scale flag for pgbench.
    
