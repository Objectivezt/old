# storage [JavaScript 的内存机制]

## 语言类型

```js
function foo(){
    var a = {name:"Objectivezt"}
    var b = a
    a.name = "劝退师" 
    console.log(a)
    console.log(b)
}
foo()
```

### 静态语言

> 在使用之前就需要确认其变量数据类型的称为静态语言。

### 动态语言

> 运行过程中需要检查数据类型的语言称为动态语言

## 隐式类型转换

> 支持隐式类型转换的语言称为弱类型语言
> 不支持隐式类型转换的语言称为强类型语言

## 数据类型特性

弱类型，意味着你不需要告诉 JavaScript 引擎这个或那个变量是什么数据类型，JavaScript 引擎在运行代码的时候自己会计算出来。
动态，意味着你可以使用同一个变量保存不同类型的数据。

### 8 种 数据类型

```js
var bar
console.log(typeof bar)  //undefined
bar = 123 
console.log(typeof bar) //number
bar = "Me"
console.log(typeof bar)//string
bar = true
console.log(typeof bar) //boolean
bar = null
console.log(typeof bar) //object
bar = {name:"me"}
console.log(typeof bar) //object
```

Boolean
Null
Undefined
Number
BigInt 新提出
String
Symbol
Object

1. 使用 typeof 检测 Null 类型时，返回的是 Object。这是当初 JavaScript 语言的一个 Bug，一直保留至今，之所以一直没修改过来，主要是为了兼容老的代码。
2. Object 类型比较特殊，它是由上述 7 种类型组成的一个包含了 key-value 对的数据类型。
3. 我们把前面的 7 种数据类型称为原始类型，把最后一个对象类型称为引用类型，之所以把它们区分为两种不同的类型，是因为它们在内存中存放的位置不一样。

### 三种类型内存空间

> 分别是代码空间、栈空间和堆空间
> 原始类型的数据值都是直接保存在“栈”中的，引用类型的值是存放在“堆”中的。

#### 栈空间

> 栈空间都不会设置太大，主要用来存放一些原始类型的小数据。

#### 堆空间

> 堆空间很大，能存放很多大的数据，不过缺点是分配内存和回收内存都会占用一定的时间。

### 赋值操作

> 原始类型的赋值会完整复制变量值，而引用类型的赋值是复制引用地址