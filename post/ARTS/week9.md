# 左耳听风 第九周

每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm
  
[自除数](https://leetcode-cn.com/problems/self-dividing-numbers/submissions/)

```javascript
let selfDividingNumbers = function(left, right) {
    let nums = [];
    for (let i = left; i <= right; i++) {
      [...i.toString()].every(val => {
        return (+val !== 0 && i % val === 0)
      }) && nums.push(i);
    }
    return nums;
};
```

## Review 

[14-major-web-development-milestones-last-20-years](http://blog.thefirehoseproject.com/posts/14-major-web-development-milestones-last-20-years/)

>整个14个发展都推动了前端的不断高速的进步

## Tip
 
[dva-cli](https://dvajs.com/knowledgemap/#%E5%88%87%E6%8D%A2-history-%E4%B8%BA-browserhistory)

> dva cli 和vue cli 一样是一个快速生成前端基础脚手架模板的工具，和create-react-app 性质类似。很多cli工具都是基于tj的commander.js 

## Share
 
[dvajs](https://dvajs.com/)
 
> 对于 redux 用户使用很友好的一个前端数据流框架， ant design pro v1 版本就是主要基于dvajs， 蚂蚁金服大佬出品。