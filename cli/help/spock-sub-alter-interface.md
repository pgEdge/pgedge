## SYNOPSIS
    ./pgedge spock sub-alter-interface SUBSCRIPTION_NAME INTERFACE_NAME DB
 
## DESCRIPTION
    Alter the subscription to use a different interface when connecting to the provider node. 

Example: spock sub-alter-interface sub_n2n1 n1_2 demo
 
## POSITIONAL ARGUMENTS
    SUBSCRIPTION_NAME
        The name of the subscription. Example: sub_n2n1
    INTERFACE_NAME
        The interface name to add to the node. Should match an interface name already created on the provider node. Example: n1_2
    DB
        The name of the database. Example: demo
