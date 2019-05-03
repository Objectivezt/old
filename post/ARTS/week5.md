# 左耳听风 第五周

> 每周完成一个ARTS： 每周至少做一个 LeetCode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[转换成小写字母](https://leetcode-cn.com/problems/to-lower-case/comments/) 

> 思路是 利用charCodeAt()方法取得Ascii值 ，如果是大写的就加32即可
```javascript
/**
 * @param {string} str
 * @return {string}
 */
var toLowerCase = function(str) {
    var res = '';
    for(let i of str){
        if(i.charCodeAt() >= 65 && i.charCodeAt() <= 90){
            i = String.fromCharCode(i.charCodeAt() + 32);
            res += i;
        }else{
            res += i;
        }
    }
    return res;
}; 
```

## Review
[13 Reasons Why React is Taking the Web Development Industry By Storm ](http://blog.thefirehoseproject.com/posts/13-reasons-react-taking-web-development-industry-storm/)

感悟:

1. 组件的模式比模板模式更好。
2. React 将函数式编程思想应用于视图层。 
3. React 让你使用新的 ES2015 语法。
4. React 使开发人员的体验非常出色。 

## Tip

 

## Share
 
