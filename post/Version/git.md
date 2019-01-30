# git 基础操作

## 为什么要用 git

    1、与cvs、svn一样都是  常见版本控制工具
    2、安全性高，开发者本地都有一套完整版本库
    3、分布式系统管理代码方便
    4、mac、linux上有操作有优势
    5、速度快于svn

## git 的基本用法

> 下载代码.

```bash
    git clone
```

- `git clone https://XXXXX.com/xxx/xxx.git` 代码会下载到 xxx 目录下;

- `git clone https://XXXXX.com/xxx/xxx.git xxx2` 代码会下载到 xxx2 目录下;

> 查看分支状态:

```bash
    git status
```

> 查看提交记录:

```bash
    git log
```

`git log filename.filetype`

> 将普通文件添加到本地 git 版本库中:

```bash
    git add
```

- `git add filename.filetype`

- `git add --all`

> 将文件拉出本地 git 版本 索引库

```bash
    git reset
```

`git reset HEAD filename.filetype`

> 查看文件修改了什么地方

```bash
    git diff
```

`git diff filename.filetype`

> 提交到本地仓库代码:

```bash
    git commit
```

> 合并本地（将远程代码仓库代码下载到本地）:

```bash
    git fetch
```

`git fetch` 默认 origin 分支

`git fetch other-branch` 下载其他分支代码

> 合并代码:

```bash
    git merge
```

> 远程仓库代码合并到当前工作分支:

```bash
    git pull
```

git pull 等于 git fetch + git merge FETCH_HEAD 很多资料说最好不要直接 git pull

> 将本地修改代码还原.

```bash
    git checkout
```

- `git checkout filename.filetype` 默认会根据 master 分支还原代码; ！！还原了以前更改就没了

- `git checkout -b xxxx-branch` 可恢复其他分支上的代码;

`git commit -m 'you commit msg'`

> 将本地代码推送到远程仓库:

```bash
    git push
```

`git push origin master`

> 重置保存密码

`git config --global credential.helper store`

> 下载指定版本的代码库

`git clone -b develop http://XXXXXXX project`

develop 为版本名

> 将某次版本到提交

`git log`

```bash
    hashKey:a4a8f75af156ca541d7e7ab0ac685d91b3f84075
```

`git checkout otherBranch`

`git cherry-pick a4a8f75af156ca541d7e7ab0ac685d91b3f84075`

> 切换远程版本

git branch -a，

列出所有分支名称如下：
`remotes/origin/dev`
`remotes/origin/release`
`git checkout -b dev origin/dev`，

作用是 checkout 远程的 dev 分支，在本地起名为 dev 分支，并切换到本地的 dev 分支
`git checkout -b release origin/release`，作用参见上一步解释

> 恢复误删到文件

例如： 误删除了根目录下的client文件夹

``` bash
    git reset HEAD
    git checkout ./client
```

## git 的不足处

    1、角色划分不明显、权限控制不足
    2、学习成本高

## git 问题处理

### 还原一个文件

1. `git status`
2. `git reset HEAD XXXX`
3. `git checkout XXXX`

XXX 为目标文件

> 例子

```bash
MacBook-Pro:layouts Objectivezt$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   ../../.vscode/settings.json
        modified:   ../common/menu.js
        modified:   ../common/router.js
        deleted:    TabController.js

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        ../containers/Home/

no changes added to commit (use "git add" and/or "git commit -a")
MacBook-Pro:layouts Objectivezt$ git reset HEAD TabController.js
Unstaged changes after reset:
M       .vscode/settings.json
M       src/common/menu.js
M       src/common/router.js
D       src/layouts/TabController.js
MacBook-Pro:layouts Objectivezt$ git checkout TabController.js
MacBook-Pro:layouts Objectivezt$ ls
BasicLayout.js          PageHeaderLayout.js     TabController.js        UserLayout.less
BlankLayout.js          PageHeaderLayout.less   UserLayout.js

```
