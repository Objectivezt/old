# this

> this 是和执行上下文绑定的

1. 执行上下文主要分为三种——全局执行上下文、函数执行上下文和 eval 执行上下文.
2. this 也只有这三种——全局执行上下文中的 this、函数中的 this 和 eval 中的 this.

## 全局执行上下文中的 this

> 在全局环境中调用一个函数，函数内部的 this 指向的是全局变量 window。
> 通过一个对象来调用其内部的一个方法，该方法的执行上下文中的 this 指向对象本身。

### 通过函数的 call 方法设置

```js
let bar = {
  myName : "Obj",
  test1 : 1
}
function foo(){
  this.myName = "NewObj"
}
foo.call(bar)
console.log(bar)
console.log(myName)
```

### 通过对象调用方法设置

>使用对象来调用其内部的一个方法，该方法的 this 是指向对象本身的。

```js

var myObj = {
  name : "object", 
  showThis: function(){
    console.log(this)
  }
}
myObj.showThis()
```

### 通过bind 和 apply 方法来设置函数执行上下文中的 this

### 通过构造函数中设置

```js
function CreateObj(){
  this.name = "object"
}
var myObj = new CreateObj()
```

## this 的设计缺陷以及应对方案

### 嵌套函数中的 this 不会从外层函数中继承

1. 嵌套函数中的 this 不会从外层函数中继承        ————————ES6 中的箭头函数来解决这个问题，把 this 体系转换为了作用域体系
2. 普通函数中的 this 默认指向全局对象 window    ————————设置 JavaScript 的“严格模式”