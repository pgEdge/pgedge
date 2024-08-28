## SYNOPSIS
    ./pgedge spock node-add-interface NODE_NAME INTERFACE_NAME DSN DB
 
## DESCRIPTION
    Add an additional interface to a spock node. 

Example: spock node-add-interface n1 n1_2 'host=10.1.2.5 user=pgedge dbname=demo' demo
 
## POSITIONAL ARGUMENTS
    NODE_NAME
        The name of the node. Should reference the node already created in this database. Example: n1
    INTERFACE_NAME
        The interface name to add to the node. The interface created by default matches the node name, add a new interface with a unique name. Example: n1_2
    DSN
        The additional connection string to the node. The user in this string should equal the OS user. This connection string should be reachable from outside and match the one used later in the sub-create command. Example: host=10.1.2.5 port= 5432 user=pgedge dbname=demo
    DB
        The name of the database. Example: demo
