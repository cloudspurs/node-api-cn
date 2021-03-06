<!-- YAML
added: v0.1.90
-->

Returns the bound address, the address family name, and port of the server
as reported by the operating system.
Useful to find which port was assigned when getting an OS-assigned address.
Returns an object with `port`, `family`, and `address` properties:
`{ port: 12346, family: 'IPv4', address: '127.0.0.1' }`

Example:

```js
var server = net.createServer((socket) => {
  socket.end('goodbye\n');
}).on('error', (err) => {
  // handle errors here
  throw err;
});

// grab a random port.
server.listen(() => {
  console.log('opened server on', server.address());
});
```

Don't call `server.address()` until the `'listening'` event has been emitted.

