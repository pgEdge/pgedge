# CLI for Service Control
Service control commands function similar to SYSTEMCTL, except they are cross-platform and also work in sandbox mode.

## Synopsis
    ./ctl service <command> [parameters] [options] 

[**start**](help/service-start.md)             - Start server components<br>
[**stop**](help/service-stop.md)               - Stop server components<br>
[**status**](help/service-status.md)           - Display status of installed server components<br>
[**reload**](help/service-reload.md)           - Reload server config files (without a restart)<br>
[**restart**](help/service-restart.md)         - Stop & then start server components<br>
[**enable**](help/service-enable.md)           - Enable a server component<br>
[**disable**](help/service-disable.md)         - Disable component from starting automatically<br>
[**config**](help/service-config.md)           - Expert only internal command for configuring a service (such as pg15)<br>
[**init**](help/service-init.md)               - Expert only internal command for initializing a service (such as pg15)<br>

## Options
    --json             # Turn on JSON output
