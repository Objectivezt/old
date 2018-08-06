# JavaScript中typeof与instanceof的区别（以前摘录网上的存在印象笔记中，现在用md写整理下）

JavaScript 中 typeof 和 instanceof 常用来判断一个变量是否为空，或者是什么类型的。

但它们之间还是有区别的：

> * `<h3>typeof</h3>`

typeof: 是一个一元运算，放在一个运算数之前，运算数可以是任意类型。

它返回值是一个字符串，该字符串说明运算数的类型。typeof 一般只能返回如下几个结果：

>number
>boolean
>string
>function
>object
>undefined

我们可以使用 typeof 来获取一个变量是否存在，eg:

```js
     if(typeof a!="undefined"){
       console.log("ok");
     }
```

but:不要去使用 if(a) 因为如果 a 不存在（未声明）则会出错，对于 Array,Null 等特殊对象使用 typeof 一律返回 object，这正是 typeof 的局限性。

> * `<h3>instanceof</h3>`

instanceof：实例,例子  用于判断一个变量是否某个对象的实例，

    ```js
    a instanceof b ? console.log("true") : console.log("false");
    ```
eg:

    ```js
    var a=new Array();
    alert(a instanceof Array);
    ```

>会返回 true，同时console.log(a instanceof Object)
>也会返回 true;这是因为 Array 是 object 的子类。

再如：

    ```js
    function test(){};
    var a=new test()
    console.log(a instanceof test)
    ```

    说道 instanceof 我们要多插入一个问题，就是 function 的 arguments，我们大家也许都认为 arguments 是一个 Array，但如果使用 instaceof 去测试会发现 arguments 不是一个 Array 对象，尽管看起来很像。

otherwise：

    ```js
    var a=new Array();
    if (a instanceof Object)
      console.log('Y');
    else
      console.log('N');//Y

    if (window instanceof Object)
      console.log('Y');
     else
      console.log('N');//N
    ```

so:这里的 instanceof 测试的 object 是指 js 语法中的 object，不是指 dom 模型对象。
使用 typeof 会有些区别`console.log(typeof(window))//object`
