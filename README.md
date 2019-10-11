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









test('makeRange throws on invalid ranges', t => {
  t.throws(() => {
    getPort.makeRange(1025, 1024);
  });
  
  t.throws(() => {
    getPort.makeRange(0, 0);
  });
  
  t.throws(() => {
    getPort.makeRange(1023, 1023);
  });
  t.throws(() => {
    getPort.makeRange(655336, 655336);
  });
});

test('makeRange produces valid ranges', t => {
  t.deepEqual([...getPort.makeRange(1024, 1024)], [1024]);
  t.deepEqual([...getPort.makeRange(1024, 1025)], [1024, 1025]);
  t.deepEqual([...getPort.makeRange(1024, 1027), [1024, 1025, 1026, 1027]]);
});
```

```
```

```
```


