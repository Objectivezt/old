# call&&apply

> - call 和 apply

    ```js
      obj.call(thisObj, arg1, arg2, ...);
      obj.apply(thisObj, [arg1, arg2, ...]);
    ```

> 其实两者作用一致，都是把 obj(即 this)绑定到 thisObj，这时候 thisObj 具备了 obj 的属性和方法。
> 或者说 thisObj『继承』了 obj 的属性和方法。绑定后会立即执行函数。
> 唯一区别是 apply 接受的是数组参数，call 接受的是连续参数。

    ```js
      function add(j, k){
          return j+k;
      }

      function sub(j, k){
          return j-k;
      }
    ```

    运行:

    ```js
    add(5,3); //8
    add.call(sub, 5, 3); //8
    add.apply(sub, [5, 3]); //8

    sub(5, 3); //2
    sub.call(add, 5, 3); //2
    sub.apply(add, [5, 3]); //2
    ```

> 调用原生对象的方法 示例：

    ```js
    var a = {0:1, 1:"zt", length: 2};

    a.slice(); //TypeError: a.slice is not a function

    Array.prototype.slice.call(a);//[1, "zt"]
    ```

> - 对象 a 类似 array，但不具备 array 的 slice 等方法。使用 call 绑定，这时候就可以调用 slice 方法。
> - 实现继承 通过 call 和 apply，我们可以实现对象继承。示例：

    ```js
    var Parent = function(){
        this.name = "zt";
        this.age = 20;
    }

    var child = {};

    console.log(child);//Object {} ,空对象

    Parent.call(child);

    console.log(child); //Object {name: "yjc", age: 22}
    ```

> - 以上实现了对象的继承。
