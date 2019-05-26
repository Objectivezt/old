# 左耳听风 第八周

每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[删除最外层的括号](https://leetcode-cn.com/problems/remove-outermost-parentheses/)

```javascript
/**
 * @param {string} S
 * @return {string}
 */
var removeOuterParentheses = function(S) {
    var left = 0, 
        right = 0;
    var tempStr = '',
        resultStr = '';
    S.split('').forEach(item => {
        if(item === '('){
            left++;
            tempStr += item;
        }else{
            right++;
            tempStr += item;
            if(left === right){
                resultStr += tempStr.slice(1,-1)
                right = 0;
                left = 0;
                tempStr = '';
            }
        }
    })
    return resultStr
};
```

## Review

[Alumni Q&A with SwitchUp: Biology Bachelor’s to Software Development](http://blog.thefirehoseproject.com/posts/biology-bachelors-to-software-development/)

感悟：越来越多跨专业转型到IT行业，保持持续学习更是转行人员需要面对的首要挑战，同时转型也是出现了很多岗位竞争压力，未来IT行业将更加兴盛。

## Tip

[在线正则表达式测试工具](http://tool.oschina.net/regex/)

[正则表达式的语法规则](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)

## Share

[wepy 框架](http://objectivezt.com/#/post/Frontends/MiniProgarm/wepy)

