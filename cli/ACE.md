# CLI for ACE
Anti Chaos Engine for a pgEdge SPOCK cluster

## Synopsis
    ./pgedge ace  <command> [parameters]

[**table-diff**](help/ace-table-diff.md)     - Efficiently compare tables across cluster using checksums and blocks of rows<br>
[**diff-schemas**](help/ace-diff-schemas.md) - Compare Postgres schemas on different cluster nodes<br>
[**diff-spock**](help/ace-diff-spock.md)     - Compare spock meta data setup on different cluster nodes<br>
[**table-repair**](help/ace-table-repair.md) - Apply changes from a table-diff source of truth to destination table<br> 
[**table-rerun**](help/ace-table-rerun.md)   - Re-run differences on the results of a recent table-diff<br>
[**repset-diff**](help/ace-repset-diff.md)   - Loop thru a replication set's tables and run table-diff on them<br>
