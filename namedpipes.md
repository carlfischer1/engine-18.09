# Using Windows named pipes

1. Run a process-isolated container with a mounted named pipe

```
.\docker run ` 
>> -it `
>> -v '\\.\pipe\docker_engine:\\.\pipe\docker_engine' `
>> -v 'c:\docker-18.09.0-ee-1-tp4\docker:c:\docker' `
>> microsoft/windowsservercore:1803 powershell
```

2. Use the CLI in the volume mount to issue commands from the container that connect to the daemon via the mounted named pipe

```
c:\docker\docker version
Client:
 Version:           18.09.0-ee-1-tp4
 API version:       1.39
 Go version:        go1.10.3
 Git commit:        f24736c
 Built:             Fri Aug 24 23:10:04 2018
 OS/Arch:           windows/amd64
 Experimental:      false

Server:
 Engine:
  Version:          18.09.0-ee-1-tp4
  API version:      1.39 (minimum version 1.24)
  Go version:       go1.10.3
  Git commit:       f24736c
  Built:            Fri Aug 24 23:25:35 2018
  OS/Arch:          windows/amd64
  Experimental:     false
```

```
c:\docker\docker image ls
REPOSITORY                    TAG                 IMAGE ID            CREATED             SIZE
microsoft/windowsservercore   1803                d03ee2083c4d        1 day ago           4.55GB
```

3. The same scenarios work with Hyper-v isolated containers

```
.\docker run ` 
>> -it `
>> -v '\\.\pipe\docker_engine:\\.\pipe\docker_engine' `
>> -v 'c:\docker-18.09.0-ee-1-tp4\docker:c:\docker' `
>> --isolation hyperv `
>> microsoft/windowsservercore:1803 powershell
```


Note: Use within `service create` is [pending](https://github.com/docker/swarmkit/pull/2691)
