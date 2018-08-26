# Windows Enterprise Engine telemetry

New telemetry.exe is installed by default with engine into `%PROGRAMFILES%\docker`. Telemetry phones home at engine start, then every 24 hours. Also included with 18.03.1-ee-3.

Opt-out methods
* Removing telemetry.exe
* Engine configuration - `%PROGRAMFILES%\docker\daemon.json`

```
{
	“telemetry-enabled” : false
}
```

Production data is available via https://docker.looker.com/looks/3324
