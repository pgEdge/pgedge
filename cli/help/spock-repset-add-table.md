## SYNOPSIS
    ./pgedge spock repset-add-table REPLICATION_SET TABLE DB <flags>
 
## DESCRIPTION
    Add a table or tables to a replication set. 

Example: spock repset-add-table demo_repset 'public.*' demo
 
## POSITIONAL ARGUMENTS
    REPLICATION_SET
        The replication set name. Example: demo_repset
    TABLE
        The name of the table(s) to add. To add all tables matching a pattern use single quotes and * as a wildcard. Examples: *, mytable, public.*
    DB
        The name of the database. Example: demo
 
## FLAGS
    -s, --synchronize_data=SYNCHRONIZE_DATA
        Synchronized table data on all related subscribers.
    
    -c, --columns=COLUMNS
        list of columns to replicate. Example: my_id, col_1, col_2
    
    -r, --row_filter=ROW_FILTER
        Row filtering expression. Example: my_id = 1001
    
    -i, --include_partitions=INCLUDE_PARTITIONS
        include all partitions in replication.
    
