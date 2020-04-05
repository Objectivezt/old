# 业务开发程序常用的 Linux 知识

> 有的业务开发同事说，我不是运维，为啥要懂 linux 基础命令？
>
> 1. 虽然生产环境上，开发不能直接操作 linux，但是测试环境阶段，问题排查往往还是由开发区解决的.
>
> 2. 要想成为团队的骨干，linux 技能是比不可少的，往往开发环境，测试环境搭建工作，往往离不开组内主力开发。
>
> 3. CI/CD 流水线配置 [docker](https://www.docker.com/) ,[Jenkins](https://jenkins.io/zh/) 离不开`linux`的常用命令

## 常见命令

```bash

echo # 输出

echo $PATH # 输出系统变量位置

tail [fileName] # 显示文件内容

touch [fileName] # 创建文件

mkdir myFolder # 创建一个叫做myFolder目录, 全称：make directory

rmdir myFolder # 删除目录  全称：remove empty directory

cd myFolder # 切换所在目录  全称：change directory

cd . # 切换当前目录

cd .. # 切换到上级目录

cd ~ # 切换到家目录

pwd # 显示当前目录

rm [fileName or folderName] # 删除文件或者目录 remove

rm -rf [fileName or folderName] # 递归强制删除所有目录

cp [fileName] [path] # 复制命令

mv [fileName] [path] # 移动文件

whereis cd # 搜索命令所在路径以及帮助文档所在位置

find / favicon.ico # 查询 / 目录下到 favicon.ico文件

whoami  # 查询自己的用户权限

history # 查看历史提交命令 修改默认查看历史命令大小 /etc/profile HISSIZE=10000

| # 管道 执行多条命令,将前一条命令的输入转为第二天命令的输出

clear # 清屏幕

```

## 命令快捷键

```bash
ctrl+c # 强制终止当前命令
ctrl+l # 清屏
ctrl+r # 在历史命令中搜索
```

## vi/ 编辑器

```bash
:q # 离开
:wq! # 保存离开

```

## 性能检查,问题排查命令

```bash

telnet # 测试远程端口是否可访问

ping # 检测主机

ps # 显示当前进程

kill [PID] # 杀死进程

top # 显示进程的实时动态

mpstat # 可以显示每个CPU的占用情况

free # 可以查看系统内存的使用情况

dmesg # 输出系统日志

```

## 常见的文件夹目录

> 大概了解即可。

| 目录名         | 解释                                               |
| :------------- | :------------------------------------------------- |
| /bin           | 存放常用命令二进制可执行文件                       |
| /home          | 用户主目录,存放所有用户文件根目录                  |
| /root          | 超级用户的主目录                                   |
| /sbin          | 存放系统管理员使用的系统级别的管理命令和程序。     |
| /dev           | 用于存放设备文件                                   |
| /mnt           | 系统管理员安装临时文件系统的安装目录               |
| /lib           | 存放跟文件系统中的程序运行所需要的共享库及内核模块 |
| /tmp           | 用于存放各种临时文件                               |
| /boot          | 存放用于系统引导时使用的各种文件                   |
| /var           | 用于存放运行时需要改变数据的文件                   |
| /opt           | 可选应用程序包所放置的位置                         |
| /proc          | 虚拟文件系统目录，内存的映射。                     |
| /usr           | 用于存放系统应用程序，有很多重要的子目录           |
| /usr/doc       | linux 文档                                         |
| /usr/man       | 帮助文档                                           |
| /usr/local/bin | 本地命令                                           |
| /usr/bin       | 应用程序                                           |
| /usr/sbin      | 超级用户的一些管理程序                             |
| /usr/local/lib | 本地库                                             |
