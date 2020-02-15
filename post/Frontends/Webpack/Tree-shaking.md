# Tree-shaking

## 概念

> 通用打包一个模块可能有多个方法，只要其中的某个方法使到了 ，则整个文件都会被打到`bundle`里面去。
> `tree shaking`就是只把用到的方法打入`bundle` ，没到到的方法会在`uglify`阶段被擦除掉

## 使用

>在`webpack4` 默认支持，借鉴了`rollup`这个工具

## 要求

> 必须是ES6 语法，  对CJS方式不支持

## 原理

> 利用ES6模块对特点

1. 只能作为模块对顶层语句出现
2. `import binging` 是 `immutable`
3. `import` 模块名只能是字符串常量
