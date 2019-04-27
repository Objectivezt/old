# 左耳听风 第四周

> 每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[二叉搜索树的范围和](https://leetcode-cn.com/problems/range-sum-of-bst)

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
 * @param {number} L
 * @param {number} R
 * @return {number}
 */

var rangeSumBST = function(root, L, R) {
    if(root === null){
        return 0;
    }
    if(root.val > R){ 
        return rangeSumBST(root.left, L, R)
    } else if(root.val < L){ 
        return rangeSumBST(root.right, L, R)
    } else{
        return root.val + rangeSumBST(root.left, L, R) + rangeSumBST(root.right,L,R);
    }
};

```

## Review

[How to Learn Web Development the Smart Way](http://blog.thefirehoseproject.com/posts/nodejs-vs-rails/)

感悟： 这是一篇4年前的文章，文中javascript框架 BackboneJS，AngularJS已经逐渐不那么流行，很多技术趋势也是再今天得到验证。

## Tip

[shell的 tree命令](http://objectivezt.com/#/post/Shell/tree)

## Share

[二级域名配置](http://objectivezt.com/#/post/ECS/secondaryDomain)
