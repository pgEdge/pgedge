CLI for Spock 
Logical and Multi-Master PostgreSQL node configuration

## Synopsis
    ./pgedge spock <command> [parameters] [options] 

[**node-create**](help/spock-node-create.md)     - Name this spock node<br>
[**node-drop**](help/spock-node-drop.md)         - Drop this spock node from the cluster<br>
[**node-alter-location**](help/spock-node-alter-location.md)	    - Set location details for spock node<br>
[**node-list**](help/spock-node-list.md)	- Display node table<br>
[**node-add-interface**](help/spock-node-add-interface.md)     - Add a new node interface<br>
[**node-drop-interface**](help/spock-node-drop-interface.md)     - Delete a node interface<br>
[**repset-create**](help/spock-repset-create.md) - Define a replication set<br>
[**repset-alter**](help/spock-repset-alter.md) - Modify a replication set<br>
[**repset-drop**](help/spock-repset-drop.md) - Drop a replication set<br>
[**repset-add-table**](help/spock-repset-add-table.md)  - Add table(s) to a replication set<br>
[**repset-remove-table**](help/spock-repset-remove-table.md)  - remove table(s) from a replication set<br>
[**repset-add-partition**](help/spock-repset-add-partition.md)  - Add partition(s) to a replication set<br>
[**repset-remove-partition**](help/spock-repset-remove-partition.md)  - remove partition(s) from a replication set<br>
[**repset-list-tables**](help/spock-repset-list-tables.md)  - List the tables in a replication set<br>
[**sub-create**](help/spock-sub-create.md)       - Create a subscription<br>
[**sub-drop**](help/spock-sub-drop.md)       - Remove a subscription<br>
[**sub-alter-interface**](help/spock-sub-alter-interface.md)	Modify an interface to a subscription<br>
[**sub-enable**](help/spock-sub-enable.md)       - Enable a subscription<br>
[**sub-disable**](help/spock-sub-disable.md)       - Disable a subscription<br>
[**sub-add-repset**](help/spock-sub-add-repset.md)     - Add replication set to a subscription<br>
[**sub-show-status**](help/spock-sub-show-status.md)        - Display the status of the subcription<br>
[**sub-show-table**](help/spock-sub-show-table.md)      - Display subscription table(s)<br>
[**sub-resync-table**](help/spock-sub-resync-table.md)     - Resynchronize a table<br>
[**sub-wait-for-sync**](help/spock-sub-wait-for-sync.md)  - Pause until subscription is synchronized<br>
[**table-wait-for-sync**](help/spock-table-wait-for-sync.md)     - Pause until a table finishes synchronizing<br>
[**replicate-ddl**](help/spock-replicate-ddl.md)     - Replicate a DDL statement<br>
[**sequence-convert**](help/spock-sequence-convert.md)     - Convert sequences to snowflake<br>
[**health-check**](help/spock-health-check.md)          - Check if PG is accepting connections<br>
[**metrics-check**](help/spock-metrics-check.md)        - Retrieve advanced DB & OS metrics<br>

