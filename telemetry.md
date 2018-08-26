# Windows Enterprise Engine telemetry

New telemetry.exe installed by default with engine into %PROGRAMDATA$\docker
Phones home at engine start, then every 24 hours
Also included with 18.03.1-ee-3

Opt-out methods
* Removing telemetry.exe
* Engine configuration - `%PROGRAMDATA%\docker\daemon.json`

```
{
	“telemetry-enabled” : false
}
```
