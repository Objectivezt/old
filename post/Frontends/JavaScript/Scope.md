# Scope

## JavaScript设计缺陷

> "变量提升"这种特性，从而导致了很多与直觉不符的代码，这也是 JavaScript 的一个重要设计缺陷
> 由于 JavaScript 需要保持向下兼容，所以变量提升在相当长一段时间内还会继续存在

### 变量提升所带来的问题

#### 变量容易在不被察觉的情况下被覆盖掉

```javascript
var myName = "objectivezt"
function showName(){
    console.log(myName);
    if(0){
        var myName = "objectivezt"
    }
    console.log(myName);
}
showName()
```

#### 本应销毁的变量没有被销毁

```javascript
function foo(){
    for (var i = 0; i < 7; i++) {

    } 
    console.log(i); 
}
foo()
```

## 克服设计缺陷

> 块级作用域并配合 let 和 const 关键字来修复这种缺陷。

### 作用域

> 作用域就是变量与函数的可访问范围，即作用域控制着变量和函数的可见性和生命周期

#### 全局作用域

> 全局作用域中的对象在代码中的任何地方都能访问，其生命周期伴随着页面的生命周期。

#### 函数作用域

> 函数作用域就是在函数内部定义的变量或者函数，并且定义的变量或者函数只能在函数内部被访问。函数执行结束之后，函数内部定义的变量会被销毁。

#### 块级作用域

> 其他语言则都普遍支持块级作用域。在 ES6 之后才支持

### const 

```js
let x = 5
const y = 6
x = 7
y = 9 //报错，const声明的变量不可以修改
```

### let

```js
function letFn() {
    let x = 1;
    if (true) {
        let x = 2; // 不同的变量
        console.log(x); // 2
    }
    console.log(x); // 1
}
```

## JavaScript 是如何支持块级作用域的

### 第一步是编译并创建执行上下文

1. 函数内部通过 var 声明的变量，在编译阶段全都被存放到变量环境里面了。
2. 通过 let 声明的变量，在编译阶段会被存放到词法环境（Lexical Environment）中。
3. 在函数的作用域内部，通过 let 声明的变量并没有被存放到词法环境中。
