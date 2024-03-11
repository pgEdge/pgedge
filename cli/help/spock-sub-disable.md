## SYNOPSIS
    ./pgedge spock sub-disable SUBSCRIPTION_NAME DB <flags>
 
## DESCRIPTION
    Disable a subscription by putting it on hold and disconnect from provider. 

Example: spock sub-disable sub_n2n1 demo
 
## POSITIONAL ARGUMENTS
    SUBSCRIPTION_NAME
        The name of the subscription. Example: sub_n2n1
    DB
        The name of the database. Example: demo
 
## FLAGS
    -i, --immediate=IMMEDIATE
        If False, sub will stop after the current transaction.
    
    -p, --pg=PG
    
    
