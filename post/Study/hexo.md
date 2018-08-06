# HEXO  学习（草稿）

>突然觉的有点迷茫，于是打算写点东西。
>>前段时间，基本掌握了docsify的用法，所以把几年前的很基础的学习的迁移了一下。

## 安装

+在Mac、Linux，安装hexo模版生成器
    `sudo npm install hexo-cli  -g`

+hexo 初始化
    `hexo  init  [your-folder-name]`

    执行后，开目录此时就自动npm install 下载依赖了， 如果没有node_modules目录就npm install 一下

## 常用命令

>在无新建Hexo项目下，控制台输入 hexo 就会出现  （自己翻译下）

    Commands:
        help     Get help on a command.
        init     Create a new Hexo folder.
        version  Display version information.

>在已经新建hexo项目下，

    Commands:
        clean     Remove generated files and cache. **清除缓存**
        config    Get or set configurations. **基础配置**
        deploy    Deploy your website. **部署网站**
        generate  Generate static files. **生成文件**
        help      Get help on a command. **获取帮助**
        init      Create a new Hexo folder. **初始化**
        new       Create a new post. **新建帖子**
        render    Render files with renderer plugins. **插件渲染**
        server    Start the server. **启动服务**
        version   Display version information. **版本信息**

>常用简写

    hexo version ===  hexo v
    hexo h === hexo === hexo hexo help
    hexo g === hexo generate
