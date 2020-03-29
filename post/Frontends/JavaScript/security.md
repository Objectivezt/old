```js
var cryptoObj = window.crypto || window.msCrypto;
var array = new Uint32Array(10);
window.crypto.getRandomValues(array);
```
