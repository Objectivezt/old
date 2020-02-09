# WXML (WeiXin Markup Language)

## WXML 语法

> 是框架设计的一套标签语言，结合组件， WSX 和事件系统，可以构建出页面结构。

属性大小写敏感，标签闭合

```wxml
<labelName attrName="attrValue">
   ...
</labelName>
```

## WXML 特性

### 属性

1. id<String> 组件的唯一标示
2. class<String> 组件内样式 wxss
3. style<String> 组件的内联样式
4. hidden<Boolean> 组件是否显示
5. data-\*<any> 自定义属性
6. bind*/catch*<EventHandler>

### 数据绑定

> Mustache 方式 {{}} 变量为小写

```wxml
<view data-name="{{attrName}}" boolean="{{flag ? true : false }}">
    {{message}}
</view>
```

```js
Page({
  data: {
    message: "Hello WXML",
    attrName: "attrValue",
    flag: true
  }
});
```

### 列表渲染

```wxml
<view>
    <block wx:for="{{items}}" wx:for-item="item" wx:key="index">
        <view>{{index}}:{{item:name}}</view>
    </block>
</view>
```

```js
Page({
  data: {
    items: [{ name: "123" }, { name: "1235" }]
  }
});
```

### 条件渲染

```wxml
<view wx:if="{{condition === 1}}">
show 1
</view>
<view wx:elif="{{condition === 2}}">
show 2
</view>
<view wx:else>
show 3
</view>
```

```js
Page({
  data: {
    condition: 1
  }
});
```

### 模块及引用

> 定义模版应用 使用 template , 导入 import include

关键字属性 name is data

两种引用模板的方式：include 和 template
区别：include 只会引用除 template 内容外的内容，
import 只会引用 template 内的的内容，动态的传入数据，is 表示引用的模板名称，data 表示传入模板的数据

```wxml
<template name="tempItem">
    <view>
       <view>attr: {{attrValue}}</view>
       <view>attr1: {{attrValue1}}</view>
    </view>
</template>

<template is="tempItem" data="{{...item}}"></template>
```

```js
Page({
  data: {
    item: {
      attrValue: "123",
      attrValue1: "2345"
    }
  }
});
```
