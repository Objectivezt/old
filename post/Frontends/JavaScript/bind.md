# bind

## 无参数

```javascript
    let a = {
        bind : function(){
            let that = this;
            let fn = function(){
                console.log(that.temp);
            }
        },
        temp : 'bind';
    }
    a.bind()
```

## 带参数

```javascript
    function fn(y,z){
        return this.x + y + z;
    }
    let method = fn.bind({x:1},2)

```