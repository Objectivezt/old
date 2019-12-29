# XMLHttpRequest 

> WebAPI——XMLHttpRequest

## 回调函数

>将一个函数作为参数传递给另外一个函数，那作为参数的这个函数就是回调函数

### 异步回调

>函数在主函数外部执行的过程称为异步回调

1. 异步函数做成一个任务，添加到信息队列尾部；
2. 把异步函数添加到微任务队列中，这样就可以在当前任务的末尾处执行微任务了。

```js
let callback = function(){
    console.log('i am objectivezt')
}
function doWork(cb) {
    console.log('start do work')
    setTimeout(cb,1000)
    console.log('end do work')
}
doWork(callback)
```

### 同步回调

>回调函数是在主函数返回之前执行的，我们把这个回调过程称为同步回调。

```js
let callback = function(){
    console.log('i am objectivezt')
}
function doWork(cb) {
    console.log('start do work')
    cb()
    console.log('end do work')
}
doWork(callback)
```

## 系统调用栈

>循环系统在执行一个任务的时候，都要为这个任务维护一个系统调用栈。这个系统调用栈类似于 JavaScript 的调用栈，只不过系统调用栈是 Chromium 的开发语言 C++ 来维护的

## 执行流程

1. 第一步：创建 XMLHttpRequest 对象。
2. 第二步：为 xhr 对象注册回调函数。
3. 第三步：配置基础的请求信息。
4. 第四步：发起请求。

```js
 function GetWebData(URL){
    /**
     * 1:新建XMLHttpRequest请求对象
     */
    let xhr = new XMLHttpRequest()

    /**
     * 2:注册相关事件回调处理函数 
     */
    xhr.onreadystatechange = function () {
        switch(xhr.readyState){
          case 0: //请求未初始化
            console.log("请求未初始化")
            break;
          case 1://OPENED
            console.log("OPENED")
            break;
          case 2://HEADERS_RECEIVED
            console.log("HEADERS_RECEIVED")
            break;
          case 3://LOADING  
            console.log("LOADING")
            break;
          case 4://DONE
            if(this.status == 200||this.status == 304){
                console.log(this.responseText);
                }
            console.log("DONE")
            break;
        }
    }

    xhr.ontimeout = function(e) { console.log('ontimeout') }
    xhr.onerror = function(e) { console.log('onerror') }

    /**
     * 3:打开请求
     */
    xhr.open('Get', URL, true);//创建一个Get请求,采用异步


    /**
     * 4:配置参数
     */
    xhr.timeout = 3000 //设置xhr请求的超时时间
    xhr.responseType = "text" //设置响应返回的数据格式
    xhr.setRequestHeader("X_TEST","objectivezt")

    /**
     * 5:发送请求
     */
    xhr.send();
}
```

## 存在的注意点

### 跨域问题

>不同源

### HTTPS 混合内容的问题

> HTTPS 混合内容是 HTTPS 页面中包含了不符合 HTTPS 安全要求的内容，比如包含了 HTTP 资源，通过 HTTP 加载的图像、视频、样式表、脚本等，都属于混合内容。
