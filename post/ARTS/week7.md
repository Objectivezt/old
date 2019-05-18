# 左耳听风 第一周

> 每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm 

[二叉树的最大深度](https://leetcode-cn.com/problems/maximum-depth-of-binary-tree/submissions/) 

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
var maxDepth = function(root) {
    if(root === null){
        return 0;
    }
    var left = maxDepth(root.left);
    var right = maxDepth(root.right);
    return Math.max(left,right) + 1;
};
```

## Review

[Why You’ll Never Be Fully Ready For Your First Developer Job](http://blog.thefirehoseproject.com/posts/why-youll-never-be-ready-for-your-first-developer-job/)

感悟：就如同刚入行时候，自己以为自己很厉害，其实哪些都是一种被小小成就感所蒙蔽。 现在的我们还只是井底之蛙，只是在努力冲向井口。

## Tip

[create-react-app](/post/Frontends/React/create-react-app.md)

## Share

### 布隆过滤器 Bloom Filter

>⼀个很长的⼆进制向量量和⼀系列列随机映射函数。布隆隆过滤器可以 用于检索⼀个元素是否在⼀个集合中。

1. 优点是空间效率和查询时间都远远超过⼀般的算法。
2. 缺点是有⼀定的误识别率和删除 困难。

>现实案例

1. 比特币网络

2. 分布式网络


