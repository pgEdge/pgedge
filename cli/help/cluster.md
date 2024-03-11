## SYNOPSIS
    ./pgedge cluster COMMAND
 
## COMMANDS
    COMMAND is one of the following:
     json-template       # Create a template for a Cluster Configuration JSON file.
     json-validate       # Validate a Cluster Configuration JSON file
     init                # Initialize a cluster via Cluster Configuration JSON file.
     replication-begin   # Add all tables in the database to replication on every node
     replication-check   # Print replication status on every node
     add-db              # Add a database to an existing pgEdge cluster.
     remove              # Remove a test cluster.
     command             # Run ./pgedge commands on one or all nodes.
     app-install         # Install test application [ pgbench | northwind ].
     app-remove          # Remove test application from cluster.
