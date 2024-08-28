## SYNOPSIS
    ./pgedge spock sub-enable SUBSCRIPTION_NAME DB <flags>
 
## DESCRIPTION
    Enable a subscription. 

Example: spock sub-enable sub_n2n1 demo
 
## POSITIONAL ARGUMENTS
    SUBSCRIPTION_NAME
        The name of the subscription. Example: sub_n2n1
    DB
        The name of the database. Example: demo
 
## FLAGS
    -i, --immediate=IMMEDIATE
        If False, sub will start after the current transaction.
    
