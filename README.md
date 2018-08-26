# engine-18.09

## Named pipes

For developers creating apps that require access to the host docker daemon, Docker on Linux has support for Unix domain socket mounting. Building the same types of apps on Windows is now supported via named pipe mounting, for both process and Hyper-v isolated containers. Hyper-v isolation support allows developers using Docker for Desktop on Windows, where all containers run using Hyper-v isolation, to build and test their app in the same way it will run in production.

[Setup and walkthrough](https://github.com/carlfischer1/engine-18.09/namedpipes.md)

## Networking




