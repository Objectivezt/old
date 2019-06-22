# 左耳听风 第十周

每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[斐波那契数](https://leetcode-cn.com/problems/fibonacci-number/submissions/)
```javascript
/**
 * @param {number} N
 * @return {number}
 */
var fib = function(N) {
    if(N === 0) {
       return 0;
    }
    if(N === 1){
        return 1;
    }
    let a = 0;
    let b = 1;
    for(var i = 1; i < N; i++){
        var temp = a;
        a = b;
        b = temp + b;
    }
    return b
};
```

## Review

## Tip

[TypeScript构建React简单应用](http://objectivezt.com/#/post/Frontends/TypeScript/TypeScript-React-Starter)

## Share