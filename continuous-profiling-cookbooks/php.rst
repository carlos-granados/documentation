Configuring Blackfire Continuous Profiler for PHP [level: Production]
======================================================================

The PHP continuous profiling is currently made accross 4 dimensions:

- **CPU Time**: time spent running on the CPU

- **Wall-time**: elapsed time per function call

- **Allocated memory**: number of bytes allocated in memory

- **Allocations**: time spent running on the CPU

Requirements
------------

- PHP >= 8.2.0

- PHP Non-Thread Safe (NTS) only

- Blackfire Agent >= 2.13.0

Installation
------------

- Download the latest `dd-library-php release <https://github.com/DataDog/dd-trace-php/releases>`_
  corresponding to your architecture.

- Extract content to ``dd-library-php`` folder.

- Find the extension in ``dd-library-php/profiling/ext/{PHP_API_VERSION}/datadog-profiling.so``
  where ``PHP_API_VERSION`` matches ``php -i | grep '^PHP API' | cut -f2 -d'='| sed 's/^> //'``

- When loaded, you can see the extension works correctly using ``php --ri datadog-profiling``

Configuration
_____________

The following environment variables are available:

- ``DD_TRACE_AGENT_URL=unix:///var/run/blackfire/agent.sock``

- ``DD_PROFILING_ENABLED=true``

- ``DD_PROFILING_LOG_LEVEL=off``

- ``DD_SERVICE="your app name"``

