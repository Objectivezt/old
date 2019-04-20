# 左耳听风 第三周

> 每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[宝石与石头](https://leetcode-cn.com/problems/jewels-and-stones/)

```javascript
var numJewelsInStones = function(J, S) {
    let res = 0;
    for(let i =0; i<S.length;i++){
        if(J.includes(S.charAt(i))){
            res += 1;
        }
    }
    return res;
};
```

## Review

[Why Every Developer Should Become a Power User of Google Chrome](http://blog.thefirehoseproject.com/posts/reactjs-101/)

文章主要介绍了：
>ReactJS的优势

1. React允许您将用户界面分解为单个组件。
2. React的单向数据流使得更新用户界面具有可预测性和可靠性。
3. 通过将生命周期中更改的所有数据保持为单个状态代码来构建用户界面，可以直观且易于理解。

>ReactJS的弱点

1. React可能会使项目的配置比较复杂。
2. 对于大多数简单的应用程序，使用原生JavaScript构建应用程序可能更简单。

## Tip

[vscode创建代码片段](http://objectivezt.com/#/post/IDE/vscode/code-snippets)

## Share

[GIT基础知识和遇到常见问题](http://objectivezt.com/#/post/Version/git)
