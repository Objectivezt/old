# 左耳听风 第二周

> 每周完成一个ARTS： 每周至少做一个 leetcode 的算法题、阅读并点评至少一篇英文技术文章、学习至少一个技术技巧、分享一篇有观点和思考的技术文章。（也就是 Algorithm、Review、Tip、Share 简称ARTS）

## Algorithm

[按奇偶排序数组](https://leetcode-cn.com/problems/sort-array-by-parity/)

```javascript
/**
 * @param {number[]} A
 * @return {number[]}
 */
var sortArrayByParity = function(A) {
	var tempArr = A;
	var sortIndexArr = [];
	var otherSortIndexArr = [];
	var returnArr = [];
	for (var index = 0; index < tempArr.length; index++) {
		if (tempArr[index] % 2 === 0) {
			// 偶数
			sortIndexArr.push(tempArr[index]);
		} else {
			// 直接将奇数放在一个数组里面
			otherSortIndexArr.push(tempArr[index]);
		}
	}
	returnArr = sortIndexArr.concat(otherSortIndexArr);
	return returnArr;
};

```

## Review

[Indeed, it seems that Google IS forgetting the old Web](http://stop.zona-m.net/2018/01/indeed-it-seems-that-google-is-forgetting-the-old-web/)

本文章讲述了，一位大佬对谷歌搜索的一些功能上的质疑。
感悟：谷歌搜索建立的搜索索引的成本变得越来越高，所以可能不得不讲一些旧的网站进行过滤。
这也是为什么文中大佬，不能搜索到过往的内容的原因。  有些实用性质的服务的确值得付费留存，解决该可能存在的问题。

## Tip

>http常见状态码

```json
{
	"200": "服务器成功返回请求的数据。",
	"201": "新建或修改数据成功。",
	"202": "一个请求已经进入后台排队（异步任务）。",
	"204": "删除数据成功。",
	"400": "发出的请求有错误，服务器没有进行新建或修改数据的操作。",
	"401": "用户没有权限（令牌、用户名、密码错误）。",
	"403": "用户得到授权，但是访问是被禁止的。",
	"404": "发出的请求针对的是不存在的记录，服务器没有进行操作。",
	"406": "请求的格式不可得。",
	"410": "请求的资源被永久删除，且不会再得到的。",
	"422": "当创建一个对象时，发生一个验证错误。",
	"500": "服务器发生错误，请检查服务器。",
	"502": "网关错误。",
	"503": "服务不可用，服务器暂时过载或维护。",
	"504": "网关超时。",
}
```

## Share

[数组和链表基本特性](http://objectivezt.com/#/post/DataStructure/ArrayLinkedList)

记录了数据结构中数组和链表基本特性