# vscode 代码片段

## 图形化界面新增

首选项 --> 用户代码片段

## 直接新增

> 以react代码片段为例

1. 根目录下新增.vscode文件夹
2. react.code-snippets

```json
{
    "scaffold services request": {
        "scope": "javascriptreact",
        "prefix": "scaffold services request",
        "body": [
            "import request from '@utils/request';",
        ],
        "description": "导入src/services 目录下文件的通用请求文件"
    }
}
```

>代码片段属性介绍

   'scaffold services request':代码片段名称
    scope: 代码作用域
    prefix: 代码提示
    body: 自定义生成片段
    description: 代码片段描述

>制表位，占位符

$number 站位符号
Tab将切换光标站位

普通占位`${1:foo}`,嵌套占位`${1:another ${2:placeholder}}`


[参考](https://code.visualstudio.com/docs/editor/userdefinedsnippets)