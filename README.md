### socket.io
---
https://github.com/socketio/socket.io

https://socket.io/get-started/chat/

```js
io.on('connection', socket => {
  socket.emit('request', /* ... */);
  io.emit('broadcast', /* ... */);
  socket.on('reply', () => { /* ... */ });
});


const server = require('http').createServer();
const io = require('socket.io')(server);
io.on('connection', client => {
  client.on('event', data => { /* ... */ });
  client.on('disconnect', () => { /* ... */ })
});
server.listen(3000);


const io = require('socket.io')();
io.on('connection', client => { ... });
io.listen(3000);


const app = require('express')();
const server = require('http').createServer(app);
io.on('connection', () => { /* ... */ });
server.listen(3000);

const app = require('koa')();
const server = require('http').createServer(app.callback());
const io = require('socket.io')(server);
io.on('connection', () => { /* ... */ });
server.listen(3000);
```

```sh
npm install socket.io
DEBUG=socket.io* node myapp
npm test
```

```js
var io = require('socket.io')(80);
var cfg = require('./config.json');
var tw = require('node-tweet-stream')(cfg);
tw.track('socket.io');
tw.track('javascript');
tw.on('tweet', function(tweet){
  io.emit('tweet', tweet);
});
```


