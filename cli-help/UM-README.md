# CLI for Update Manager
Update Manager is similar in function to YUM & APT.  It is consistent across platforms & also works in sandbox mode.

## Synopsis
    ./pgedge um <command> [parameters] [options] 

[**list**](doc/um-list.md) - Display available/installed components<br>
[**update**](doc/um-update.md)  - Retrieve new list of components & update ctl<br>
[**install**](doc/um-install.md) - Install a component (eg pg16, spock32, postgis, ...)<br>
[**remove**](doc/um-remove.md) - Un-install component<br>
[**upgrade**](doc/um-upgrade.md) - Perform an upgrade of a component<br>
[**clean**](doc/um-clean.md) - Delete downloaded component files from local cache<br>

## Options
    --json             # Turn on JSON output
    --debug            # Turn on debug logging
    --silent           # Less noisy
    --verbose or -v    # More noisy

