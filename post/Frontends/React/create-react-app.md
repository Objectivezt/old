# 使用 create-react-app 构建一个web应用

## 创建

### 使用npx创建

> npm > 5.2

```bash

npx create-react-app my-react-app

```

### 使用npm创建

> npm 6 + 

```bash

npm init react-app my-app

```

### 使用yarn 构建

> yarn 0.25+

```bash

yarn create react-app my-app

```

##基础目录

│  .gitignore
│  package-lock.json
│  package.json
│  README.md
│
├─public
│      favicon.ico
│      index.html
│      manifest.json
│
└─src
        App.css
        App.js
        App.test.js
        index.css
        index.js
        logo.svg
        serviceWorker.js


## 执行脚本

package.json
```json
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
```

### npm run start 

> 启动程序

### npm run build

> 打包程序

### npm run test 

> 执行测试脚本

### npm run eject

> 用户能完全取得 webpack 文件的控制权,主要是更改 webpack 配置


## 其他脚手架

[dva](https://dvajs.com/)
[rekit](http://rekit.js.org/)