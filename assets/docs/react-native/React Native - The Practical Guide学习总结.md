# React Native - The Practical Guide 学习总结

![](./RN-pratical.jpg)

#### 视频地址：[React Native 上](https://www.bilibili.com/video/BV1FP4y1M7j2?p=1) [React Native 下](https://www.bilibili.com/video/BV18q4y1Y7M5?p=1)

#### github 练习：[RN-practice](https://github.com/linzhishui/RN-practice)

本课程的讲师是 Maximilian Schwarzmüller，他是一位知名的前端开发讲师，以其深入浅出、注重细节的教学风格而受到许多学生的喜爱。他的多门课程涵盖了一系列前端开发技术，包括 React、React Native、Typescript、Angular 等，适用于不同水平的学生。

在 React Native 课程中，他注重解释 RN 的基本概念，从搭建环境到实际应用开发，都有详细的讲解。这对初学者来说非常友好，因为初学者通常需要对技术栈的方方面面有一个全面而深入的了解。

他的讲解风格被描述为不急不缓，这对于初学者来说是非常重要的。慢而稳的节奏让学生更容易理解和吸收知识，避免了学习过程中的困扰和迷茫感。

本课程总计 19 个章节，视频时长 28 个半小时。

## 第一章

首先介绍了 RN 的一些概念，RN 由两块内容组成：一些特别的 React 组件，这些组件会被编译成原生 Widgets、另一块是原生平台的 APIs。注意只有 UI 会编译成原生代码，逻辑不会被编译。我们写的 Javascript 代码之后会跑在 RN App 的一个 Javascript 线程中，我们的 Javascript 代码通过 Javascript 虚拟机，虚拟机再通过 Bridge 与原生模块交互。

另外，RN 的理念是 "Learn once, Write everywhere"，IOS 与 Android 下实现同一样式可能使用的是不同的方法，这当中的差异需要开发人员来手动敲代码各自实现，RN 并不会自动实现。

搭建环境有两个 选项，一个是 React Native CLI ，这个是使用 RN 自己的命令行工具来初始化 RN 应用，用此方法时，如果你没有 macOS 系统，不借助第三方软件下你是无法构建 iOS App 的，这是硬件的限制。此外还需要安装各种各样的包，安装的过程非常非常的折腾。。。可能很多同学就卡在这步，然后就没有然后了。

官方搭建环境文档：[React Native Environment Setup](https://www.reactnative.cn/docs/environment-setup)

作为初学者，我们一般使用 Expo CLI 来初始化项目，Expo 是围绕 RN 的一套工具集，Expo 解决了 Windows 开发者无法构建 iOS 的问题，此外简化了环境配置，使用 Expo 来构建 RN App 可以大大的提高效率。课程中使用的也就是 Expo 构建的方案。

## 第二章

本章的任务，就是熟悉 RN 内部组件的使用，最基础的 7 个组件如下：

1. View：用于布局的容器组件。
2. Text：用于显示文本。
3. Image：用于显示图片。
4. ScrollView：滚动视图，用于展示滚动的内容。
5. TextInput：文本输入框。
6. StyleSheet：样式表，用于定义组件的样式。
7. Touchable 系列组件：用于捕捉用户的触摸操作，例如 TouchableHighlight、TouchableOpacity 等。

## 第三章

本章讲解了如何调试 RN 程序，有以下方法：

1. 使用 React DevTools 进行调试。
2. 在模拟器或设备上启用调试模式。
3. 使用 console.log()输出调试信息。
4. 使用 React Native Debugger 工具进行高级调试。

## 第四章

本章以一个猜数字 App 为例子，以项目为目的开发 RN 程序，除了进一步复习组件与样式外，还增加了加载静态资源、键盘控制等方法。

具体内容包括：

1. 创建猜数字 App 的项目结构。
2. 实现猜数字逻辑与用户交互。
3. 加载并显示静态资源，如图片和字体。
4. 处理键盘输入与控制。

## 第五章

本章是对第四章实现的猜数字 APP 的调整，适配程序在小屏、旋转下的正确展示，并根据不同平台设置不同的样式。

具体内容包括：

1. 响应屏幕旋转事件，调整布局。
3. 使用 Platform 模块识别当前运行的平台，设置不同的样式。

## 第六章

RN 中导航与 Web 中导航最大区别，就是没有 URL 这个概念了，所以配置路由的方法与 Web 中根据 URL 映射组件的方法略有不同。

具体内容包括：

1. 使用 React Navigation 库进行导航管理。
2. 配置导航器与屏幕之间的映射关系。
3. 实现堆栈导航、底部导航等常见导航模式。
4. 处理导航参数传递与接收。

本视频使用的 react-navigation 版本是 4.x，但最新版本已经是 7.x。

为了先熟悉学习课程，目前还是保持使用 4.x 版本进行编程。

当前遇到了阻塞：

安装 npm install react-navigation-tabs

在 MealsNavigator.js 中导入引用 import { createBottomTabNavigator } from 'react-navigation-tabs';

刷新程序就直接报错如下：

<u>ERROR TypeError: \_ReanimatedModule.default.createNode is not a function (it is undefined), js engine: hermes</u>

<u>ERROR Invariant Violation: "main" has not been registered. This can happen if:</u>

- <u>Metro (the local dev server) is run from the wrong folder. Check if Metro is running, stop it and restart it in the current project.</u>
- <u>A module failed to load due to an error and `AppRegistry.registerComponent` wasn't called., js engine: hermes</u>
