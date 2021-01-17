# mumble-web

INSTRUCTION
---------------------

This version use the projet of EvertRamos : docker-compose-letsencrypt-nginx-proxy-companion

Please install first Mumble Server with NGINX and Let's Encrypt
https://github.com/Tofdu31/docker-mumble-nginx-letsencrypt

    git clone https://github.com/Tofdu31/docker-mumble-nginx-letsencrypt
    
Configure files projet Mumble Server
---------------------

mumble-web is an HTML5 [Mumble] client for use in modern browsers.

### FIRST !!! INSTALL MUMBLE with NGINX and Let's Encrypt : https://github.com/Tofdu31/docker-mumble-nginx-letsencrypt

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
2. Edit end configure .env
3. Start with : docker-compose up (or docker-compose up -d)

### License
ISC

[Mumble]: https://wiki.mumble.info/wiki/Main_Page
[mumble-web-proxy]: https://github.com/johni0702/mumble-web-proxy
[MetroMumble]: https://github.com/xPoke/MetroMumble
[Matrix]: https://matrix.org
