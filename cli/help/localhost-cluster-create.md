## SYNOPSIS
    ./pgedge localhost cluster-create CLUSTER_NAME NUM_NODES <flags>
 
## DESCRIPTION
    Create a localhost cluster. Each node will be located in the cluster/<cluster_name>/<node_name> directory. Each database will have a different port. 

Example: localhost cluster-create demo 3 -U lcusr -P lcpasswd -d lcdb
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
    NUM_NODES
        The number of nodes in the cluster.
 
## FLAGS
    --pg=PG
        The PostgreSQL version of the database.
    
    --port1=PORT1
        The starting port for this cluster. For local clusters, each node will have a port increasing by 1 from this port number.
    
    -U, --User=USER
        The username of the superuser created for this database.
    
    -P, --Passwd=PASSWD
        The password for the above user.
    
    -d, --db=DB
        The database name.
    
    -a, --auto_ddl=AUTO_DDL
        Auto DDL on or off
    
