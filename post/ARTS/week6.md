# 左耳听风 第六周

> 每周完成一个ARTS： 每周至少做一个 LeetCode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[有序数组的平方](https://leetcode-cn.com/problems/to-lower-case/comments/) 

> 思路是 利用charCodeAt()方法取得Ascii值 ，如果是大写的就加32即可
```javascript
/**
 * @param {number[]} A
 * @return {number[]}
 */
var sortedSquares = function(A) {
    return A.map(x=>Math.pow(x,2)).sort((x,y)=>x-y)
};
```

## Review

## Tip

### bash 常用特殊符号

`~`  ⽤户家⽬录
`-`  标准输⼊(/dev/stdin)
`.`  当前⽬录
`..` 上层⽬录
`.file`  隐藏⽂件，需要通过ls -a查看
`|` 管道符，⽤于联通两个命令，前⼀个的输出作为后⼀个的输⼊
`&` 出现在命令末尾，代表该命令后台运⾏
`$` $VAR是取变量VAR的值，不存在则为空
`;` 标识⼀条命令的结束（默认是换⾏符标识命令结束）
`<>`  输⼊/输出重定向

                                ———————— 《鸟哥的Linux私房菜》

## Share

[segmentfault抵制CSDN](https://segmentfault.com/a/1190000019120547?utm_source=ad_index)

看法：在中国互联网起步初期，技术社区、论坛的建设, 可能需要一些外部收入支持（如广告，会员），然而互联网版权意识越来越强，社区盈利模式需要做一定的转型，才能顺应当前潮流。



 
