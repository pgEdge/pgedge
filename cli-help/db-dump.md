## SYNOPSIS
    ./pgedge db dump OBJECT SOURCE_DSN <flags>
 
## DESCRIPTION
    object: database or database.schema.object where schema and object can contain wildcard '*'
source_dsn: host=x, port=x, username=x (in any order)
file: location and file name for dump
schema_only: do not include data in the pg_dump
 
## POSITIONAL ARGUMENTS
    OBJECT
    SOURCE_DSN
 
## FLAGS
    -f, --file=FILE
    
    
    -s, --schema_only=SCHEMA_ONLY
    
    
    -p, --pg=PG
    
    
