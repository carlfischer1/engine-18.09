# Installing the 18.09 TP4 engine on Windows Server

1. On a Windows Server 1803 host, open a PowerShell window

2. If an existing version of Docker EE is installed, remove it

`uninstall-package docker -provider dockermsftprovider`

3. Download the TP4 build

`Invoke-WebRequest -URI "https://s3-us-west-2.amazonaws.com/internal-docker-ee-builds/windows-server/18.09/docker-18.09.0-ee-1-tp4.zip" -usebasicparsing -outfile docker-18.09.0-ee-1-tp4.zip`

`expand-archive docker-18.09.0-ee-1-tp4.zip c:\`

`cd \docker-18.09.0-ee-1-tp4\docker`

5. Start and switch to a second Powershell window to run the daemon

`.\dockerd.exe -D`

6. Switch to the first Powershell window and verify Docker is running

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
