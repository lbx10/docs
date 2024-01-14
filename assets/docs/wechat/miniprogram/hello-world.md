# 微信小程序开发

## 环境申请搭建

上[微信息公众平台](https://developers.weixin.qq.com/miniprogram/dev/framework/)申请相关资格

使用[微信开发者工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html)开发

其它略

## 目录

[参考](https://www.ruanyifeng.com/blog/2020/10/wechat-miniprogram-tutorial-part-one.html)

![工程目录](assets/images/wechat-miniprogram/hello-catalog.jpg)

最基本的元素是 app.json、app.js|ts、pages/xx/xx.wxml、pages/xx/xx.js|ts

## 项目配置文件 app.json

顶层的 app.json 文件用于整个项目的配置，对于所有页面都有效。

其中，pages 是必须的，关联了每一个页面。window 属性是配置小程序的窗口的配置，包含导航栏的颜色、导航栏的文字颜色、导航栏的文字等等

其它的还有底部 tab 的配置等

## pages 目录

页面相关代码，一般一个页面一个文件夹，名称按惯例与文件夹名字一致，按功能使用相关后缀即可
