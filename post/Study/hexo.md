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

    >在无新建Hexo项目下，控制台输入 hexo 就会出现

    Commands:
        help     Get help on a command.
        init     Create a new Hexo folder.
        version  Display version information.

    Global Options:
        --config  Specify config file instead of using _config.yml
        --cwd     Specify the CWD
        --debug   Display all verbose messages in the terminal
        --draft   Display draft posts
        --safe    Disable all plugins and scripts
        --silent  Hide output on console

    >在已经新建hexo项目下，

    Commands:
        clean     Remove generated files and cache.
        config    Get or set configurations.
        deploy    Deploy your website.
        generate  Generate static files.
        help      Get help on a command.
        init      Create a new Hexo folder.
        list      List the information of the site
        migrate   Migrate your site from other system to Hexo.
        new       Create a new post.
        publish   Moves a draft post from _drafts to _posts folder.
        render    Render files with renderer plugins.
        server    Start the server.
        version   Display version information.

    Global Options: 相同

    >常用简写

    hexo version ===  hexo v
    hexo h === hexo === hexo hexo help
    hexo g === hexo generate

