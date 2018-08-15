# ES3 ES5

## 判断 this 的指向

> 优先级递减

1. 函数被new调用，this 指向`new`构造出的新对象
2. 函数通过`bind()`、`apply()`、`bind()`,`his只想被绑定的对象
3. 函数做方法被调用，this指向对象的上下文
4. 非严格模式下，this会指向`window`，严格模式下this会指向`underfined`
