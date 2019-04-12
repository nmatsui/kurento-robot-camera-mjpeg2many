# kurento-robot-camera-mjpeg2many
This application send a camera stream of remote Motion JPEG Server to browser(s) by using [Kurento](http://www.kurento.org/).

[![Docker image size](https://img.shields.io/microbadger/image-size/nmatsui/kurento-robot-camera-mjpeg2many.svg)](https://hub.docker.com/r/nmatsui/kurento-robot-camera-mjpeg2many/)

## Description
This Kurento application transmits a remote camera stream which is served as Motion JPEG to browser(s) by using WebRTC.

## Requirements
||version|
|:--|:--|
|kurento|6.9.0|
|nodejs|8.15|
|docker|18.09.2|

## How to build
1. `npm install`
2. `npm run build`

## Environment Variables

|env|sample value|
|:--|:--|
|`PORT`|3000|
|`KURENTO_URL`|http://`LOCAL_IP_ADDRESS`:8888/kurento|
|`PASS_PHRASE`|your-own-pass-phrase|
|`STUN_LIST`||
|`TURN_LIST`||

## How to run
1. start Kurento container.
    * `docker run -d -p 8888:8888 kurento/kurento-media-server:6.9.0`
2. set environment variables.
3. start mjpeg2many application.
    * `node ./dist/server.js`
4. open the mjpeg2many application page by browser.
    * http://localhost:3000/
5. enter `passPhrase` which is set as an environment variable.
6. enter the URL of Motion JPEG Server.
7. click `start` button.

## License

[Apache License 2.0](/LICENSE)

## Copyright
Copyright (c) 2019 Nobuyuki Matsui <nobuyuki.matsui@gmail.com>
