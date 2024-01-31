# React 入门

### 推荐学习视频 1：https://www.bilibili.com/video/BV1wy4y1D7JT/?spm_id_from=333.337.search-card.all.click&vd_source=8320e7c5479e39861db9cce844452b05

### 推荐学习视频 2：https://www.bilibili.com/video/BV1ZB4y1Z7o8/?spm_id_from=333.337.search-card.all.click&vd_source=8320e7c5479e39861db9cce844452b05

### 官网：https://react.docschina.org/

## 什么是 React？

React 由 Facebook 研发；用于解决 UI 复杂度的开源 JavaScript 库。

> 它不是框架，只是为了解决 UI 复杂度而诞生的一个库

## React 的特点

- 轻量：核心库源码轻量，仅 3000 多行
- 原生：所有的 React 的代码都是用原生 JS 书写而成的，不依赖其他任何库
- 易扩展：React 对代码的封装程度较低，所以 React 中的很多功能都可以扩展。
- 不依赖宿主环境：React 只依赖原生 JS 语言。因此，它可以被轻松的移植到浏览器、桌面应用、移动端。
- 无侵入性：与 angular 和 Vue 不同，React 在定义上并非框架，对整个工程没有强制约束力。这对与那些已存在的工程，可以逐步的将其改造为 React，而不需要全盘重写。（Vue：https://cn.vuejs.org/）
- 用 JS 代码声明界面
- 组件化

## 对比 Vue

|   对比项   | Vue | React |
| :--------: | :-: | :---: |
| 全球使用量 |     |   ✔   |
| 国内使用量 |  ✔  |       |
|    性能    |  ✔  |   ✔   |
|   易上手   |  ✔  |       |
|   灵活度   |     |   ✔   |
|  大型企业  |     |   ✔   |
| 中小型企业 |  ✔  |       |
|    生态    |     |   ✔   |

# Hello World

直接在页面上使用 React，引用下面的 JS

```html
<script
  crossorigin
  src="https://unpkg.com/react@16/umd/react.development.js"
></script>
<script
  crossorigin
  src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"
></script>
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```

## React.createElement

创建一个 React 元素，称作虚拟 DOM，本质上是一个对象

1. 参数 1：元素类型，如果是字符串，一个普通的 HTML 元素
2. 参数 2：元素的属性，一个对象
3. 后续参数：元素的子节点

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>

  <body>
    <div id="root"></div>
    <!-- React的核心库，与宿主环境无关 -->
    <script
      crossorigin
      src="https://unpkg.com/react@16/umd/react.development.js"
    ></script>
    <!-- 依赖核心库，将核心的功能与页面结合 -->
    <script
      crossorigin
      src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"
    ></script>
    <!-- 编译JSX -->
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
    <script>
      //创建一个span元素
      var span = React.createElement("span", {}, "一个span元素");
      //创建一个H1元素
      var h1 = React.createElement(
        "h1",
        {
          title: "第一个React元素",
        },
        "Hello",
        "World",
        span
      );
      ReactDOM.render(h1, document.getElementById("root"));
    </script>
  </body>
</html>
```

## JSX

JS 的扩展语法，需要使用 babel 进行转义。

# 使用脚手架搭建工程

官方：create-react-app

后续会有第三方脚手架使用学习

凡是使用 JSX 的文件，必须导入 React

```js
import React from "react";
import ReactDOM from "react-dom";

ReactDOM.render(
  <h1>
    Hello World <span>span元素</span>
  </h1>,
  document.getElementById("root")
);
```

## Chrome 插件安装

React Developer Tools---直接在插件商店查找，对 chrome 版本有要求
