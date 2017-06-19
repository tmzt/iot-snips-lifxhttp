# iot-snips-lifxhttp

Daemon for managing LIFX lights (using HTTP API) with Snips AI platform

Build and run as a docker container on your Raspberry PI or other device running Snips.ai.

This implementation uses the Lifx HTTP library and requires an API token from https://cloud.lifx.com/settings.

Running with Docker on the Raspberry PI
---------------------------------------

These instructions are designed to be used after following the tutorial at https://github.com/snipsco/snips-platform-documentation/wiki.

Checkout this repository and run `docker build -t iot-snips-lifxhttp .` to build the container.

Create a file /opt/iot-snips-lifxhttp/config.json containing:

   {
     "mqtt_host": "172.17.0.1",
     "mqtt_port": 9898,
     "lifx_token": "YOUR API TOKEN"
   }

Run `docker run -d -v /opt/iot-snips-lifxhttp:/app/config --log-driver none --rm --name snips-lifx iot-snips-lifxhttp`.


*NOTE: Not associated with Lifi Labs, Inc. or snips.ai. Based on examples from https://github.com/snipsco/snips-platform-documentation/blob/master/node/.*
