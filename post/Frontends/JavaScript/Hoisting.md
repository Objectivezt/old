# 变量提升 (Hoisting)

## 执行上下文

> 变量提升、作用域和闭包 都和执行上下文，息息相关

```javascript
    showName()
    console.log(myName)
    var myName = 'myName'
    function showName() {
        console.log('showName function was executed');
    }
```

```console

```

```javascript
    showName()
    console.log(myName) // ReferenceError  
    function showName(){
        console.log('showName function was executed');
    }
```

``` console
    Uncaught ReferenceError
```

1. 在执行过程中，若使用了未声明的变量，那么 JavaScript 执行会报错。
2. 在一个变量定义之前使用它，不会出错，但是该变量的值会为 undefined，而不是定义时的值。
3. 在一个函数定义之前使用它，不会出错，且函数能正确执行。

## 原理

> 所谓的变量提升，是指在 JavaScript 代码执行过程中，JavaScript 引擎把变量的声明部分和函数的声明部分提升到代码开头的“行为”。变量被提升后，会给变量设置默认值，这个默认值就是我们熟悉的 undefined

## JavaScript 代码的执行流程

1. 编译阶段
   >输入一段代码，经过编译后，会生成两部分内容：执行上下文（Execution context）和可执行代码。
   1. 第一部分：变量提升部分的代码。
   2. 第二部分：执行部分的代码。
2. 执行阶段
   >按照顺序一行一行地执行

### 代码中出现相同的变量或者函数怎么办

一段代码如果定义了两个相同名字的函数，那么最终生效的是最后一个函数
