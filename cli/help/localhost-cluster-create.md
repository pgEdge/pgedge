## SYNOPSIS
    ./pgedge localhost cluster-create CLUSTER_NAME NUM_NODES <flags>
 
## DESCRIPTION
    Create a local cluster. Each node will be located in the cluster/<cluster_name>/<node_name> directory. Each database will have a different port. 

Example: cluster local-create demo 3 lcusr lcpasswd 16 6432 lcdb
 
## POSITIONAL ARGUMENTS
    CLUSTER_NAME
        The name of the cluster.
    NUM_NODES
        The number of nodes in the cluster.
 
## FLAGS
    --pg=PG
        The postgreSQL version of the database.
    
    --port1=PORT1
        The starting port for this cluster. For local clusters, each node will have a port increasing by 1 from this port number.
    
    -U, --User=USER
    
    
    -P, --Passwd=PASSWD
    
    
    -d, --db=DB
        The database name.
    
        Below is an example of the JSON file that is generated that defines a 2 node localhost cluster
    
        { "name": "cl1", "style": "localhost", "create_date": "2024-02-23", "localhost": { "os_user": "rocky", "ssh_key": "" }, "database": { "databases": [ { "username": "lcusr", "password": "lcpasswd", "name": "lcdb" } ], "pg_version": "16" }, "node_groups": { "localhost": [ { "nodes": [ { "name": "n1", "is_active": true, "ip_address": "127.0.0.1", "port": 6432, "path": "/home/rocky/dev/cli/out/posix/cluster/cl1/n1" } ] }, { "nodes": [ { "name": "n2", "is_active": true, "ip_address": "127.0.0.1", "port": 6433, "path": "/home/rocky/dev/cli/out/posix/cluster/cl1/n2" } ] } ] }
    
