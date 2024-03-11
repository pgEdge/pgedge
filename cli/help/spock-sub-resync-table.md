## SYNOPSIS
    ./pgedge spock sub-resync-table SUBSCRIPTION_NAME RELATION DB <flags>
 
## DESCRIPTION
    Resynchronize one existing table. 

Example: spock sub-resync-table sub_n2n1 mytable demo
 
## POSITIONAL ARGUMENTS
    SUBSCRIPTION_NAME
        The name of the subscription. Example: sub_n2n1
    RELATION
        Table name. Example: mytable
    DB
        The name of the database. Example: demo
 
## FLAGS
    -t, --truncate=TRUNCATE
        WARNING: If this is set to True, the function will truncate the table immediately, and only then begin synchronising it, so it will be empty while being synced.
    
    -p, --pg=PG
    
    
