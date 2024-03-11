# CLI for Service Control
Service control commands function similar to SYSTEMCTL, except they are cross-platform and also work in sandbox mode.

## Synopsis
    ./ctl service <command> [parameters] [options] 

[**start**](doc/service-start.md)             - Start server components<br>
[**stop**](doc/service-stop.md)               - Stop server components<br>
[**status**](doc/service-status.md)           - Display status of installed server components<br>
[**reload**](doc/service-reload.md)           - Reload server config files (without a restart)<br>
[**restart**](doc/service-restart.md)         - Stop & then start server components<br>
[**enable**](doc/service-enable.md)           - Enable a server component<br>
[**disable**](doc/service-disable.md)         - Disable component from starting automatically<br>
[**config**](doc/service-config.md)           - Expert only internal command for configuring a service (such as pg15)<br>
[**init**](doc/service-init.md)               - Expert only internal command for initializing a service (such as pg15)<br>

## Options
    --json             # Turn on JSON output
