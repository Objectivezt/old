# async && await

> 解决问题： 从 Promise 代码可以看出来，使用 promise.then 也是相当复杂，虽然整个请求流程已经线性化了，但是代码里面包含了大量的 then 函数，使得代码依然不是太容易阅读。

## ES7 特性

### async/await

> ES7 引入了 async/await，这是 JavaScript 异步编程的一个重大改进，提供了在不阻塞主线程的情况下使用同步代码实现异步访问资源的能力，并且使得代码逻辑更加清晰。

```js
async function foo() {
  try {
    let response1 = await fetch("https://www.objectievzt.com");
    console.log("response1");
    console.log(response1);
    let response2 = await fetch("https://www.objectievzt.com");
    console.log("response2");
    console.log(response2);
  } catch (err) {
    console.error(err);
  }
}
foo();
```

### 生成器（Generator）

> 关联技术：
> async/await 使用了 Generator 和 Promise 两种技术， Generator 的底层实现机制——协程（Coroutine）

> 生成器函数是一个带星号函数，而且是可以暂停执行和恢复执行的

```js
function* genDemo() {
  console.log("开始执行第一段");
  yield "generator 2";

  console.log("开始执行第二段");
  yield "generator 2";

  console.log("开始执行第三段");
  yield "generator 2";

  console.log("执行结束");
  return "generator 2";
}

console.log("main 0");
let gen = genDemo();
console.log(gen.next().value);
console.log("main 1");
console.log(gen.next().value);
console.log("main 2");
console.log(gen.next().value);
console.log("main 3");
console.log(gen.next().value);
console.log("main 4");
```

1. 在生成器函数内部执行一段代码，如果遇到 yield 关键字，那么 JavaScript 引擎将返回关键字后面的内容给外部，并暂停该函数的执行。
2. 外部函数可以通过 next 方法恢复函数的执行。

## 协程（Coroutine）

> 协程是一种比线程更加轻量级的存在。
> 如果从 A 协程启动 B 协程，我们就把 A 协程称为 B 协程的父协程。

1. 通过调用生成器函数 genDemo 来创建一个协程 gen，创建之后，gen 协程并没有立即执行。
2. 要让 gen 协程执行，需要通过调用 gen.next。
3. 当协程正在执行的时候，可以通过 yield 关键字来暂停 gen 协程的执行，并返回主要信息给父协程。
4. 如果协程在执行期间，遇到了 return 关键字，那么 JavaScript 引擎会结束当前协程，并将 return 后面的内容返回给父协程。

> 需要关注以下内容。
> 第一点：gen 协程和父协程是在主线程上交互执行的，并不是并发执行的，它们之前的切换是通过 yield 和 gen.next 来配合完成的。
> 第二点：当在 gen 协程中调用了 yield 方法时，JavaScript 引擎会保存 gen 协程当前的调用栈信息，并恢复父协程的调用栈信息。同样，当在父协程中执行 gen.next 时，JavaScript 引擎会保存父协程的调用栈信息，并恢复 gen 协程的调用栈信息。

## async

> 根据 MDN 定义，async 是一个通过异步执行并隐式返回 Promise 作为结果的函数。对 async 函数的理解，这里需要重点关注两个词：异步执行和隐式返回 Promise

```js
async function foo() {
  return 3;
}
console.log(foo()); // Promise {<resolved>: 3}
```

## await

```js
async function foo() {
  console.log(1);
  let a = await 100;
  console.log(a);
  console.log(2);
}
console.log(0);
foo();
console.log(3);
```

await 100 时，会默认创建一个 Promise 对象
回调函数被激活后
将主线程控制权交给 foo 协程，并将 value 值传给协程

```js
let promise_ = new Promise((resolve,reject){
  resolve(100)
})


promise_.then((value)=>{
})
```
