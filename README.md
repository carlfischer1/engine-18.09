# engine-18.09

## Installation

[Installing EE 18.09 TP4 for Windows Server](https://github.com/carlfischer1/engine-18.09/blob/master/installation.md)

### When EE 18.09 is GA

As of 18.03.1, installing the Enterprise Engine for Windows Server supports two channels: 17.06 and 18.03, with 17.06 as the default. With the Q3 release three channels will be supported, with the default channel changing to 18.09.

Specifying a channel at install time, or changing to a different channel: https://docs.docker.com/install/windows/docker-ee/

## Named pipes

For developers creating apps that require access to the host docker daemon, Docker on Linux has support for Unix domain socket mounting. Building the same types of apps on Windows is now supported via named pipe mounting, for both process and Hyper-v isolated containers. Hyper-v isolation support allows developers using Docker for Desktop on Windows, where all containers run using Hyper-v isolation, to build and test their app in the same way it will run in production.

[Setup and walkthrough](https://github.com/carlfischer1/engine-18.09/blob/master/namedpipes.md)

## Networking



## Telemetry

Extensive effort has gone into providing usage telemetry for Docker EE engines running on Linux distributions. While implemented differently, we now have equivalent telemetry for Docker EE engines running on Windows Server.

[Setup and walkthrough](https://github.com/carlfischer1/engine-18.09/blob/master/telemetry.md)

