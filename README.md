# mumble-web

<p align="center">
    <img src="TEMPLATE MUMBLE SERVER.png" alt="Docker Mumble WEB NGINX LET'S ENCRYPT" >

<p align="center">
  Docker image for Mumble web.
</p>

INSTRUCTION
---------------------

Please install first Mumble Server with NGINX and Let's Encrypt
https://github.com/Tofdu31/docker-mumble-nginx-letsencrypt

    
Configure files projet Mumble Server
---------------------

mumble-web is an HTML5 [Mumble] client for use in modern browsers.

The Mumble protocol uses TCP for control and UDP for voice.
Running in a browser, both are unavailable to this client.
Instead Websockets are used for control and WebRTC is used for voice (using Websockets as fallback if the server does not support WebRTC).

In WebRTC mode (default) only the Opus codec is supported.

In fallback mode, when WebRTC is not supported by the server, only the Opus and CELT Alpha codecs are supported.
This is accomplished with libopus, libcelt (0.7.1) and libsamplerate, compiled to JS via emscripten.
Performance is expected to be less reliable (especially on low-end devices) than in WebRTC mode and loading time will be significantly increased.

Quite a few features, most noticeably all
administrative functionallity, are still missing.

### Installing

1. Clone this repositories

    git clone https://github.com/Tofdu31/docker-mumble-nginx-letsencrypt

2. Edit end configure .env
3. Start with : docker-compose up (or docker-compose up -d)

### Running the Container
---------------------

In order to persist configuration data when upgrading your container you should create a named data
volume. This is not required but is _highly_ recommended.

    docker volume create --name slice

And

    docker-compose up -d

### License
ISC

[Mumble]: https://wiki.mumble.info/wiki/Main_Page
[mumble-web-proxy]: https://github.com/johni0702/mumble-web-proxy
[MetroMumble]: https://github.com/xPoke/MetroMumble
[Matrix]: https://matrix.org
