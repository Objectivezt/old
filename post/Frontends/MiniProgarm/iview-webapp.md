# iview webapp

> iview 的微信小程序组件

## 使用

1. 他们的github官网，下载源码。（在我写帖子时候这里比较暂时还没有，使用npm 直接安装的方式）
2. 将源码打包一下，我看他的package 中的脚本 是使用了gulp构建的，可以看例子。
3. 把dist目录下文件取出(源码中npm run build 就会进行构建，在build目录下有该文件，生产dist目录)
4. 迁移到自己项目中（现在官方还没有初npm 或者 yarn down依赖，略有不方便之处）

## 引入

自己拿来玩的项目是使用的wpy框架，下面就是引入方式了，路径写个alias也行

```js
 export default class Index extends wepy.page {
  config = {
    navigationBarTitleText: 'test',
    usingComponents: {
      'i-button': '../components/iview//button/index',
      'i-progress': '../components/iview/progress/index',
      'i-icon': '../components/iview/icon/index'
    }
  };
  //.....
 }
```

```html
<template>
    <i-button>123
    </i-button>
</template>
```