# WEBXR Testbed

Fully working instance of WebXR + VRTK.

The result of completing the FusedVR WebXR tutorials:
- [Part 1](https://www.youtube.com/watch?v=nPAHZ9Rm8d4&t=0s)
- [Part 2](https://www.youtube.com/watch?v=RKpa2tDvNiQ)

# Dependencies

- nodejs
- openssl
- npm
- [nodejs http-server](https://www.npmjs.com/package/http-server)
- Git Bash (already has tools to build https certs built in)

# Usage

Follow the Part 1 tutorial above for building instructions, it may involve setting some project settings and WebGL templates.

WebXR needs to be on an **https** server (http**S**!) to run correctly. You need a certificate to spin up an https server. Create it by using Git Bash to navigate to the root of the build folder you specified in Unity, then enter:

`openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem`

Following that, spin up the server with:

`http-server -S -C cert.pem`

On your WebXR device (Quest etc.) navigate to your computer's local IP address followed by the port specified by the server. For example using the http-server default port: `https://192.168.0.xxx:8080`. 
