## SYNOPSIS
    ./pgedge spock sub-create SUBSCRIPTION_NAME PROVIDER_DSN DB <flags>
 
## DESCRIPTION
    Create a subscription. 

Example: spock sub-create sub_n2n1 'host=10.1.2.5 port=5432 user=pgedge dbname=demo' demo
 
## POSITIONAL ARGUMENTS
    SUBSCRIPTION_NAME
        The name of the subscription. Each subscription in a cluster must have a unique name. Example: sub_n2n1
    PROVIDER_DSN
        The connection string to the node that this node will subscribe to. The user in this string should equal the OS user. This connection string should be reachable from this node and match the one used previously in the node-create command. Example: host=10.1.2.5 port= 5432 user=pgedge dbname=demo
    DB
        The name of the database. Example: demo
 
## FLAGS
    -r, --replication_sets=REPLICATION_SETS
        An array of replication sets to automatically include in this subscription. Example: demo_repset,default,default_insert_only,ddl_sql
    
    --synchronize_structure=SYNCHRONIZE_STRUCTURE
        Synchronize structure on subscription create. If some objects already exist in this database then the create of the subscription will fail.
    
    --synchronize_data=SYNCHRONIZE_DATA
        Synchronize data on subscription create.
    
    -f, --forward_origins=FORWARD_ORIGINS
        For multimaster, this should be kept at the default. For replicating everything written to a node, transactions replicated to it included, this can be set to all.
    
    -a, --apply_delay=APPLY_DELAY
        The amount of time to delay the replication.
    
    -p, --pg=PG
    
    
