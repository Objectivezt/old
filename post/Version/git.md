# git基础操作

## 为什么要用git
  
    1、与cvs、svn一样都是  常见版本控制工具
    2、安全性高，开发者本地都有一套完整版本库
    3、分布式系统管理代码方便
    4、mac、linux上有操作有优势
    5、速度快于svn

## git的基本用法

>下载代码.

```bash
    git clone
```

* `git clone https://XXXXX.com/xxx/xxx.git`   代码会下载到xxx目录下;

* `git clone https://XXXXX.com/xxx/xxx.git xxx2` 代码会下载到xxx2目录下;

> 查看分支状态:

```bash
    git status
```

>查看提交记录:

```bash
    git log
```

`git log filename.filetype`

>将普通文件添加到本地git版本库中:

```bash
    git add
```

* `git add filename.filetype`
  
* `git add --all`
  
>将文件拉出本地git版本 索引库

```bash
    git reset
```

`git reset HEAD filename.filetype`

>查看文件修改了什么地方

```bash
    git diff
```

`git diff filename.filetype`

>提交到本地仓库代码:

```bash
    git commit
```

>合并本地（将远程代码仓库代码下载到本地）:

```bash
    git fetch
```

 `git fetch` 默认 origin 分支

 `git fetch other-branch` 下载其他分支代码

>合并代码:

```bash
    git merge
```

>远程仓库代码合并到当前工作分支:

```bash
    git pull
```

git pull  等于 git fetch + git merge FETCH_HEAD  很多资料说最好不要直接git pull

>将本地修改代码还原.

```bash
    git checkout
```

* `git checkout filename.filetype` 默认会根据master分支还原代码;  ！！还原了以前更改就没了
  
* `git checkout -b xxxx-branch` 可恢复其他分支上的代码;

`git commit -m 'you commit msg'`

>将本地代码推送到远程仓库:

```bash
    git push
```

`git push origin master`

## git的不足处

    1、角色划分不明显、权限控制不足
    2、学习成本高