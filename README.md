# Pusher WebRTC Video Chat

This is a demo WebRTC application for peer-to-peer chat, meaning you don't necessarily need an Internet connection to send messages. It uses the Pusher realtime API for signalling, allowing devices to discover each other and make a connection using WebRTC.

There's a [demo showing this in action](https://webrtc-chat-demo.herokuapp.com/), as well as a [full tutorial on how to create something like this](http://pusher.com/tutorials/webrtc_chat) yourself.

## Servers

You can use any server to pass-through the Pusher messages. This demo provides a few of the most common platforms.

### /src/_servers/nodejs

The server code required to run the demo using [Node.js](http://nodejs.org/).

The `src/js/datachannel-demo.js` file by default is set up to send AJAX requests to the Node.js server.

You'll need to change the config values in `src/_servers/nodejs/config.example.js` and rename it to `config.js`, as well as changing the `PUSHER_APP_KEY` value in `src/js/datachannel-demo.js`.

You can then get up and running by running the following commands in the terminal:

```
$ cd /path/to/your/app/src/_servers/nodejs
$ npm install
$ node app.js
```
    
And navigating to http://localhost:5001 to see the side-by-side example or http://localhost:5001/chat.html to see the standalone example.

## Security

It's worth noting that the default __PHP server setup__ in this demo will potentially leave the demo config files for other platforms open to being read. It's highly recommended to implement strict control over which files can be read from your server, or moving the server files into a directory outside of public reach.

_When using this demo in your own production environment, you should remove the servers you don't need and ensure that config files aren't readable to the public._
