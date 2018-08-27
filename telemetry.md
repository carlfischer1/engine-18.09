# Windows Enterprise Engine telemetry

Telemetry phones home at engine start, then every 24 hours. Also included with 18.03.1-ee-3. The data reported is identical to that with Linux EE engines.

Opt-out
* POST-TP4: Features in engine configuration:

`echo '{"features":{"telemetry":true}}' > %PROGRAMFILES%\docker\daemon.json`

To verify state, at daemon startup, in debug log look for:

`DEBU[2018-08-27T17:19:08.099327900Z] Docker daemon will send anonymous usage telemetry`

Production data is available via https://docker.looker.com/looks/3324
