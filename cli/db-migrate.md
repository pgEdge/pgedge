## SYNOPSIS
    ./pgedge db migrate OBJECT SOURCE_DSN TARGET_DSN <flags>
 
## DESCRIPTION
    object: database.schema.object where schema and object can contain wildcard '*'
source_dsn: host=x, port=x, username=x, password=x, database=x (in any order)
target_dsn: host=x, port=x, username=x, password=x, database=x (in any order)
schema_only: do not include data in the pg_dump
 
## POSITIONAL ARGUMENTS
    OBJECT
    SOURCE_DSN
    TARGET_DSN
 
## FLAGS
    -s, --schema_only=SCHEMA_ONLY
    
    
    -p, --pg=PG
    
    
