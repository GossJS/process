# process
Веб-сервер как процесс

```JavaScript
let s;
let p;
let u = '/qqq';
let f = './index.js';

s = require('http')
.Server(({ url: r }, rs) => {
  if (r === u) {
    s.close();
    rs.end(require('fs').readFileSync(f));
  } else {
    rs.end ('hola ' + p + ' ' + r);
  }
});

s.listen(1234, () => {
  p = process.pid;
});

process.stdout.write('ok ');
```
