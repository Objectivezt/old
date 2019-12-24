# Stack overflow

## 当一段代码被执行时，JavaScript 引擎先会对其进行编译，并创建执行上下文

1. 当 JavaScript 执行全局代码的时候，会编译全局代码并创建全局执行上下文，而且在整个页面的生存周期内，全局执行上下文只有一份.
2. 当调用一个函数的时候，函数体内的代码会被编译，并创建函数执行上下文，一般情况下，函数执行结束之后，创建的函数执行上下文会被销毁.
3. 当使用 `eval` `函数的时候，eval` 的代码也会被编译，并创建执行上下文.

## 调用栈

>用来管理函数调用关系的一种数据结构

### 状态

>入栈、栈满、出栈、空栈和再次入栈

### js 调用栈

>在执行上下文创建好后，JavaScript 引擎会将执行上下文压入栈中，通常把这种用来管理执行上下文的栈称为执行上下文栈，又称调用栈。

## Chrome 调试

### 如何利用浏览器查看调用栈的信息

console.trace() 来输出当前的函数调用关系

### 栈溢出

> 调用栈有两个指标，最大栈容量和最大调用深度(12574)，满足其中任意一个就会栈溢出

调用栈是有大小的，当入栈的执行上下文超过一定数目，JavaScript 引擎就会报错，我们把这种错误叫做栈溢出。
