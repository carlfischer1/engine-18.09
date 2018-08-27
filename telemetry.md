# Windows Enterprise Engine telemetry

Telemetry phones home at engine start, then every 24 hours. Also included with 18.03.1-ee-3. The data reported is identical to that with Linux EE engines.

Opt-out
* POST-TP4: Features in engine configuration:

`echo '{"features":{"telemetry":true}}' > %PROGRAMFILES%\docker\daemon.json`

* To verify state, at daemon startup look for:

`INFO[2018-08-23T14:58:21.443100742Z] starting telemetry service`

* Production data:

https://docker.looker.com/looks/3324
