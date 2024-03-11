CLI for Spock 
Logical and Multi-Master PostgreSQL node configuration

## Synopsis
    ./pgedge spock <command> [parameters] [options] 

[**node-create**](doc/spock-node-create.md)     - Name this spock node<br>
[**node-drop**](doc/spock-node-drop.md)         - Drop this spock node from the cluster<br>
[**node-alter-location**](doc/spock-node-alter-location.md)	    - Set location details for spock node<br>
[**node-list**](doc/spock-node-list.md)	- Display node table<br>
[**node-add-interface**](doc/spock-node-add-interface.md)     - Add a new node interface<br>
[**node-drop-interface**](doc/spock-node-drop-interface.md)     - Delete a node interface<br>
[**repset-create**](doc/spock-repset-create.md) - Define a replication set<br>
[**repset-alter**](doc/spock-repset-alter.md) - Modify a replication set<br>
[**repset-drop**](doc/spock-repset-drop.md) - Drop a replication set<br>
[**repset-add-table**](doc/spock-repset-add-table.md)  - Add table(s) to a replication set<br>
[**repset-remove-table**](doc/spock-repset-remove-table.md)  - remove table(s) from a replication set<br>
[**repset-add-seq**](doc/spock-repset-add-seq.md)     - Add a sequence to a replication set<br>
[**repset-remove-seq**](doc/spock-repset-remove-seq.md)     - Remove a sequence from a replication set<br>
[**repset-alter-seq**](doc/spock-repset-alter-seq.md)     - Change a replication set sequence<br>
[**repset-list-tables**](doc/spock-repset-list-tables.md)  - List the tables in a replication set<br>
[**sub-create**](doc/spock-sub-create.md)       - Create a subscription<br>
[**sub-drop**](doc/spock-sub-drop.md)       - Remove a subscription<br>
[**sub-alter-interface**](doc/spock-sub-alter-interface.md)	Modify an interface to a subscription<br>
[**sub-enable**](doc/spock-sub-enable.md)       - Enable a subscription<br>
[**sub-disable**](doc/spock-sub-disable.md)       - Disable a subscription<br>
[**sub-add-repset**](doc/spock-sub-add-repset.md)     - Add replication set to a subscription<br>
[**sub-show-status**](doc/spock-sub-show-status.md)        - Display the status of the subcription<br>
[**sub-show-table**](doc/spock-sub-show-table.md)      - Display subscription table(s)<br>
[**sub-sync**](doc/spock-sub-sync.md)     - Synchronize a subscription<br>
[**sub-resync-table**](doc/spock-sub-resync-table.md)     - Resynchronize a table<br>
[**spock-sub-wait-for-sync**](doc/spock-sub-wait-for-sync.md)  - Pause until subscription is synchronized<br>
[**table-wait-for-sync**](doc/spock-table-wait-for-sync.md)     - Pause until a table finishes synchronizing<br>
[**health-check**](doc/spock-health-check.md)          - Check if PG is accepting connections<br>
[**metrics-check**](doc/spock-metrics-check.md)        - Retrieve advanced DB & OS metrics<br>


## Options
    --json             # Turn on JSON output
    --debug            # Turn on debug logging
    --silent           # Less noisy
    --verbose or -v    # More noisy

