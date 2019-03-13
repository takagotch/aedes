### aedes
---
https://github.com/mcollina/aedes

```js
var aedes = require('aedes')()
var server = require('net').createServer(aedes.handle)
var port = 1883

server.listen(port, function() {
  console.log('server litening on port', port)
})


var fs = require('fs')
var aedes = require('aedes')()

var options = {
  key: fs.readFileSync('YOUR_TLS_KEY_FILE.pem'),
  cert: fs.readFileSync('YOUR_TLS_CERT_FILE.pem')
}

var server = require('tls').createServer(options, aedes.handle)

server.listen(8883, function () {
  console.log('server started and listening on port 8883')
})


var aedes = require('./aedes')()
var server = require('net').createServer(aedes.handle)


instance.authenticate = function (client, username, password, callback) {
  callback(null, username === 'matteo')
}

instance.authenticate = function (client, username, password, callback) {
  var error = new Error('Auth error')
  error.returnCode = 1
  callback(error, null)
}

instance.authorizePublish = funciton (client, packet, callback) {
  if (packet.topic === 'aaaa') {
    return callback(new Error('wrong topic'))
  }
  
  if (packet.topic === 'bbb') {
    packet.payload = new Buffer('overwrite packet payload')
  }
  
  callback(null)
}


instance.authorizeSubscribe = funciton (client, sub, callback) {
  if (sub.topic === 'aaaa') {
    return callback(new Error('wrong topic'))
  }
  
  if (sub.topic === 'bbb') {
    sub.qos = sub.qos + 2
  }
  
  callbakck(null, sub)
}


insance.authorizeSubscribe = funciton = funciton (client, sub, callback) {
  if (sub.topic === 'aaaa') {
    sub = null
  }
  
  callback(null, sub)
}








```

```
npm install aedes --save
```

```
{
  cmd: 'publish',
  qos: 2,
  topic: 'test',
  payload: new Buffer('test'),
  retain: false
}
```


