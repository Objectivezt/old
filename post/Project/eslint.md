# eslint 笔记

## 使用

### 安装

```bash
    npm i eslint -D 
```

或

```bash
    npm i eslint --save-dev
```

或

package.json

```json
    {
        //...
        "devDependencies":{
            "eslint": "4.0.0"
        }
        //...
    }
```

```bash
 npm install
```

### 创建

创建生成    .eslintrc

```bash
eslint --init
```

### 运行

```bash
eslint myfile.js
```

## 文件配置

### env

>环境信息

```js
{
    env:{
        browser: true,
        node: true,
        es6: true,
        mocha: true,
        jest: true,
        jasmine: true,
    }
}
```

### globals

>相关的全局变量

```js
    {
        globals:{
            jsx:true,
            wx:true,
        }
    }
```

### rules

#### config

>规则信息

eslint官方提供了3种预安装包：

##### eslint-config-google

```bash
  npm install eslint eslint-config-google -g
```

##### eslint-config-airbnb

>首先需要查看其依赖版本 , 因为它依赖eslint, eslint-plugin-import, eslint-plugin-react, and eslint-plugin-jsx-a11y等插件，并且对各个插件的版本有所要求。

输入：

```bash
    npm info "eslint-config-airbnb@latest" peerDependencies
```

输出：

```bash
{ eslint: '^4.19.1',
  'eslint-plugin-import': '^2.12.0',
  'eslint-plugin-jsx-a11y': '^6.0.3',
  'eslint-plugin-react': '^7.9.1' }
```

安装：

```bash
npm install eslint@4.19.1 eslint-plugin-import@2.12.0 eslint-plugin-jsx-a11y@6.0.3  eslint-plugin-react@7.9.0 --save-dev
```

##### eslint-config-standard

  ```bash
     npm install eslint-config-standard eslint-plugin-standard eslint-plugin-promise -g
  ```

##### 自定义

可以根据官方文档查看

### extends

```js
//多个
{
  extends: ['airbnb', 'prettier'],
}
//单个
{
  extends:'eslint-config-react-app',
}
  
```

> 配置文件信息

### 配置项目注释

常用的

```js
//eslint-disable-line
```