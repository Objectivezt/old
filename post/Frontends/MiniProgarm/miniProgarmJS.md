# 各个环境中的 JavaScript 和 WSX

## ECMAScript

> 语法 + 类型 + 语句 + 关键字 + 操作符 + 对象

## Nodejs 中的 JavaScript

> ECMAScript + Native + NPM

## 小程序的 JavaScript

> ECMAScript + 小程序框架 + 小程序 API

## 浏览器的 JavaScript

> ECMAScript + BOM + DOM

## 小程序运行环境

1. IOS JavascriptCore
2. Android X5 内核
3. IDE nodeWebkitJS

## WSX

> 模块
> 变量
> 注释
> 运算符
> 语句
> 数据类型
> 基础类库

```wxml
<wxs module="m1">
    module.exports = {
        message: 'Hello, world'
    }
</wxs>

<view>{{m1.message}}</view>

<wxs src="./m1.wsx" modules="m2"></wxs>
<view>{{m2.message}}</view>
```

```wxs
// m2.wxs
modules.exports = require('./m1.wxs')

//m1.wxs
modules.exports = {
    message: "hello"
}
```

### 运算符

1. 等值运算符
2. 赋值运算符
3. 二元运算符号
4. 基本运算符
5. 位运算符
6. 比较运算符

### 数据类型

1. number
2. string
3. boolean
4. object
5. array
6. function
7. date
8. regexp

### 基础类库

1. Number
2. Date
3. Global
4. console
5. Math
6. JSON

### 和 JS 区别

不支持 try catch
