# webpack 学习笔记

>webpack是模块打包器

1、通过打包.less, .sass, .jsx, .vue, img等等文件进行打包。

2、将有依赖类型相关文件打包成浏览器识别的文件。

3、能进行文件分割、按需加载相关依赖.

4、自定义打包方式

>与其他打包器不优势

+loader

+插件系统

+模块热更新

## 基本使用

+新建一个项目

```bash
mkdir webpack-test
npm init
npm i webpack -D
```

得到一个package.json 文件

+构建配置文件webpack.config.js

```js
module.export = {
    //...
}
```

### extry （入口文件）

```js
module.export = {
    extry: './src/index.js',//入口
}
```

### output （输出位置）

```js
module.export = {
     output:{
        path: '/dist',//输出
        filename: 'js/[name].bundle.js'
    },
}
```

### loader （加载器）

>这是一个消耗时间非常长打包过程

#### babel-loader

```bash
 npm install -D babel-preset-lastest
```

```js
   module.export = {
       module:{
           loaders:[
               {
                   test:/\.js$/, //匹配文件
                   loader:'babel', //loaderming
                   exclude:'./node-modules' //排除文件
                   include:'./src'  //需要打包的位置
                   query:{
                       presets:['lastest']  
                   }// 匹配的版本
               }
           ]
       }
   }
```

```.babelrc
{
    preset:[es2015]
}
```

#### css loader

### plugins （插件）

```js

const htmlWebpackPlugin = require('html-webpack-plugin');
module.export = {
    plugins: [
        new htmlWebpackPlugin({
            filename:'index.html',
            template:'index.html',
            inject:'body'
        })
    ]
}
```

## 其他

### 使用绝对路径

```js
const path = requrie('path');

path.resolve( __diranme,'')
```