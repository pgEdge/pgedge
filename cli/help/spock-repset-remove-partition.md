## SYNOPSIS
    ./pgedge spock repset-remove-partition PARENT_TABLE DB <flags>
 
## DESCRIPTION
    Remove a partition from the replication set that the parent table is a part of. 

Example: spock repset-remove-partition mytable demo --partition=mytable_202012
 
## POSITIONAL ARGUMENTS
    PARENT_TABLE
        The name of the parent table. Example: mytable
    DB
        The name of the database. Example: demo
 
## FLAGS
    --partition=PARTITION
        The name of the partition. If none is provided, it will remove all replicated partitions from the replication set. Example: mytable_202012
    
    --pg=PG
    
    
