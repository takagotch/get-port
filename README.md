### get-port
---
https://github.com/sindresorhus/get-port

```js
// test.js
import {promisify} from 'util';
import net from 'net';


test('port can be bound when promise resolves', async t => {
  const port = await getPort();
  t.is(typeof port, 'number');
  t.true(port > 0);
  
  const server = net.createServer();
  await promisify(server.listen.bind(server))(port);
  
  t.is(server.address().port, port);
});





```

```
```

```
```


