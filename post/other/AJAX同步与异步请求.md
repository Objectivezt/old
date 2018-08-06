# AJAX同步与异步请求

> 同步与异步
    > 1. 从web表单中获取需要的数据
    > 2. 建立要连接的URL
    > 3. 打开到服务器的连接
    > 4. 设置服务器在完成后要运行的函数
    > 5. 发送请求

```js
    //创建核心对象
    function createXHR(){
        //兼容性测试
        if(window.XMLHttpRequest){
            return new XMLHttpRequest();//ie7+,chrome...
        }else{
            return new ActiveXObject("Microsoft.XMLHTTP");
        }
    }
    //封装一个Ajax方法
    /**
      *@param: method  方法
      *        url     地址
      *        async   异步
    */
    function Ajaxbyzt(method,url,async){
        var xhr = new createXHR();
        xhr.open(method,url,async);
        xhr.send();
        //异步——true
        if(async){
            xhr.onreadystatechange = function(){
                //判断readyState和status状态  4和200
                if(xhr.readyStatus == 4){
                    if(xhr.status == 200){
                        xhr.responseText;
                    }
                }
            }
        }else{
            //判断同步
            if(xhr.status==200){
                return xhr.responseText;
            }
        }
    }
```