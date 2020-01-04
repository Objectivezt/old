# WebComponent

##  那什么是组件化呢？
对内高内聚，对外低耦合。对内各个元素彼此紧密结合、相互依赖，对外和其他组件的联系最少且接口简单。

##  阻碍前端组件化的因素
需要确保第三方的内容样式不会影响到当前内容，同样也要确保当前的  DOM  不会影响到第三方的内容。

## WebComponent 组件化开发
它提供了对局部视图封装能力，可以让  DOM、CSSOM  和  JavaScript  运行在局部环境中，这样就使得局部的  CSS  和  DOM  不会影响到全局。

> WebComponent  是一套技术的组合，具体涉及到了  Custom elements（自定义元素）、Shadow DOM（影子  DOM）和 HTML templates（HTML  模板）

1、使用  template  属性来创建模板
2、我们需要创建一个 MyName 类
￼ 查找模板内容；
￼ 创建影子  DOM；
￼ 再将模板添加到影子  DOM  上。
3、可以像正常使用  HTML  元素一样使用该元素

＃#  影子  DOM

> 影子  DOM  的作用主要有以下两点：
> 1、影子  DOM  中的元素对于整个网页是不可见的；
> 2、影子  DOM  的  CSS  不会影响到整个网页的  CSSOM，影子  DOM  内部的  CSS  只对内部的元素起作用。
