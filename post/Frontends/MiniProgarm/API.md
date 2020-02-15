# WeApp API

## 类型

1. 网络
2. 媒体
3. 文件
4. 数据缓存
5. 位置
6. 设备
7. 界面
8. 开放接口

## 规则

wx.on
Object 参数
wx.get/wx.set

status:

    1. suceess
    2. fail
    3. complete

函数———— 直调函数，回调函数

## 主要协议

1. HTTP

   > 是基于 TCP/IP 通信协议通过万维网服务传输数据到本地浏览器的应用层协议

2. websocket
   > 是由 HTML5 规范提出的一种在单个 TCP 连接上进行全双工通信的应用层协议

## 版本要求

    IOS 6.5.21
    Android 6.5.19
    基础库版本 1.7.0

## 登录授权

> code 和 session_key 为一一对应关系
> session_key 有时效性

## 微信支付

> 设置密钥并下载客户证书
> 确认 web 服务器 https 服务

## 消息模版

> 推送位置 —— 服务通知
> 下发条件 —— 支付/提交表单
> 跳转能力 —— 小程序各个页面
