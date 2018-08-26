# engine-18.09

## Named pipes

For developers creating apps that require access to the host docker daemon, Docker on Linux has support for Unix domain socket mounting. Building the same types of apps on Windows is now supported via named pipe mounting, for both process and Hyper-v isolated containers. Hyper-v isolation support allows developers using Docker for Desktop on Windows, where all containers run using Hyper-v isolation, to build and test their app in the same way it will run in production.

[Setup and walkthrough](https://github.com/carlfischer1/engine-18.09/blob/master/namedpipes.md)

## Networking



## Telemetry

Extensive effort has gone into providing usage telemetry for Docker EE engines running on Linux distributions. While implemented differently, we now have equivalent telemetry for Docker EE engines running on Windows Server.

[Setup and walkthrough](https://github.com/carlfischer1/engine-18.09/blob/master/telemetry.md)

