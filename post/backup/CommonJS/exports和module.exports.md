require 用来加载代码，而 exports 和 module.exports 则用来导出代码。

**test.js**

```js
var a = {name: 1}
var b = a

console.log(a)
console.log(b)

b.name = 2
console.log(a)
console.log(b)

var b = {name: 3}
console.log(a)
console.log(b)
```

运行 test.js 结果为：

```
{ name: 1 }
{ name: 1 }
{ name: 2 }
{ name: 2 }
{ name: 2 }
{ name: 3 }
```

**解释**：a 是一个对象，b 是对 a 的引用，即 a 和 b 指向同一块内存，所以前两个输出一样。当对 b 作修改时，即 a 和 b 指向同一块内存地址的内容发生了改变，所以 a 也会体现出来，所以第三四个输出一样。当 b 被覆盖时，b 指向了一块新的内存，a 还是指向原来的内存，所以最后两个输出不一样。

exports 和 module.exports 的区别了：

1. module.exports 初始值为一个空对象 {}
2. exports 是指向的 module.exports 的引用
3. require() 返回的是 module.exports 而不是 exports

#### exports = module.exports = {...}

我们经常看到这样的写法：

```js
exports = module.exports = {...}
```

上面的代码等价于:

```js
module.exports = {...}
exports = module.exports
```

原理很简单：module.exports 指向新的对象时，exports 断开了与 module.exports 的引用，那么通过 exports = module.exports 让 exports 重新指向 module.exports。
