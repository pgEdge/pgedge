## SYNOPSIS
    ./pgedge spock node-create NODE_NAME DSN DB
 
## DESCRIPTION
    Create a spock node. 

Example: spock node-create n1 'host=10.1.2.5 user=pgedge dbname=demo' demo
 
## POSITIONAL ARGUMENTS
    NODE_NAME
        The name of the node. Only one node is allowed per database, and each node in a cluster must have a unique name. To use snowflake, use the convention n1,n2, etc. Example: n1
    DSN
        The connection string to the node. The user in this string should equal the OS user. This connection string should be reachable from outside and match the one used later in the sub-create command. Example: host=10.1.2.5 port= 5432 user=pgedge dbname=demo
    DB
        The name of the database. Example: demo
