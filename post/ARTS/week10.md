# 左耳听风 第十周

每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[合并二叉树](https://leetcode-cn.com/problems/merge-two-binary-trees/comments/)

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} t1
 * @param {TreeNode} t2
 * @return {TreeNode}
 */
var mergeTrees = function(t1, t2) {
     function dfs(t1, t2){
        if(!t1) return t2;
        if(!t2) return t1;
        t1.val = t1.val + t2.val;
        t1.left = dfs(t1.left, t2.left);
        t1.right = dfs(t1.right, t2.right);
        return t1;
    }
    return dfs(t1, t2);
};
```

## Review

[is-technology-making-a-positive-impact-on-society](http://blog.thefirehoseproject.com/posts/is-technology-making-a-positive-impact-on-society/)

> 人工职能 将不断改变人们的生活，同时也会带来一些伦理问题。

## Tip

### Ant Design 常用组件属性配置

>Card

```js
export default {
    type: 'inner',
    hoverable: true,
    bordered: true
};
```

>Col

```js
export default {
    sm: 24,
    md: 12,
    lg: 8,
    xl: 8,
    xll: 6,
};
```

>Table

```js
export default {
    bordered: true,
    size: 'small',
    showHeader: true
};
```

>Select

```js
export default {
    showSearch: true,
    optionFilterProp: 'children',
    allowClear: true,
    placeholder: '请选择或输入',
    style: { width: '85%' }
};
```

>Pagination

```js
export default {
    showSizeChanger: true,
    showQuickJumper: true,
    pageSizeOptions: ['1', '5', '10', '20', '30', '50', '100', '200']
};

```

>Modal

```js
export default {
    width: 1024,
    destroyOnClose: true,
    zIndex: 20,
    mask: true,
    maskClosable: false,
    keyboard: true,
    centered: true
};
```

## Share

[花瓣](https://huaban.com/search)

>一个对于前端和设计师提升，艺术灵感和美感的网站
>
>