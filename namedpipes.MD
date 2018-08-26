# Using Windows named pipes

## Setup

1. On a Windows Server 1803 host, open a PowerShell window

2. Download the TP4 build

`Invoke-WebRequest -URI "https://s3-us-west-2.amazonaws.com/internal-docker-ee-builds/windows-server/18.09/docker-18.09.0-ee-1-tp4.zip" -usebasicparsing -outfile c:\docker-18.09.0-ee-1-tp4.zip`

3. Extract and run the engine

`expand-archive c:\docker-18.09.0-ee-1-tp4.zip`
`cd c:\docker-18.09.0-ee-1-tp4\docker`

4. Start and switch to a second Powershell window to run the daemon

`.\dockerd.exe -D`

5. Switch to the first Powershell window and verify Docker is running

```
.\docker.exe version
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
  
## Try it out

6. Run a process-isolated container with a mounted named pipe

```
.\docker run ` 
>> -it `
>> -v '\\.\pipe\docker_engine:\\.\pipe\docker_engine' `
>> -v 'c:\docker-18.09.0-ee-1-tp4\docker:c:\docker' `
>> microsoft/windowsservercore:1803 powershell
```

7. Now inside the container, use the CLI in the volume mount to issue commands that connect to the daemon via the mounted named pipe

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

8. The same scenarios work with Hyper-v isolated containers

```
.\docker run ` 
>> -it `
>> -v '\\.\pipe\docker_engine:\\.\pipe\docker_engine' `
>> -v 'c:\docker-18.09.0-ee-1-tp4\docker:c:\docker' `
>> --isolation hyperv `
>> microsoft/windowsservercore:1803 powershell
```
