# React 组件

## JSX

- Facebook 起草的 JS 扩展语法
- 本质与 JS 没有区别，会被 babel 编译，React 相关语法糖最终会被转换为 React.createElement
- 每个 JSX 表达式，有且仅有一个根节点
  - React.Fragment
- 每个 JSX 元素必须结束（XML 规范），允许自结束。

## 在 JSX 中嵌入表达式

- 在 JSX 中使用注释
- 将表达式作为内容的一部分
  - null、undefined、false 不会显示
  - 普通对象，不可以作为子元素
  - 可以放置 React 元素对象
- 将表达式作为元素属性
- 属性使用小驼峰命名法
- 防止注入攻击
  - 自动编码
  - dangerouslySetInnerHTML

## 元素的不可变性

- 虽然 JSX 元素是一个对象，但是该对象中的所有属性不可更改
- 如果确实需要更改元素的属性，需要重新创建 JSX 元素

## 组件和组件属性

组件：包含内容、样式和功能的 UI 单元

## 创建一个组件

**特别注意：组件的名称首字母必须大写**

1. 函数组件

返回一个 React 元素

```js
import React from "react";

export default function MyFuncComp() {
  return <h1>函数组件</h1>;
}
```

2. 类组件

必须继承 React.Component

必须提供 render 函数，用于渲染组件

```js
import React from "react";

export default class MyClassComp extends React.Component {
  render() {
    return <h1>类组件的内容</h1>;
  }
}
```

## 组件的属性

1. 对于函数组件，属性会作为一个对象的属性，传递给函数的参数

```js
import React from "react";

export default function MyFuncComp(props) {
  // return <h1>函数组件的内容</h1>
  return <h1>函数组件，目前的数字：{props.number}</h1>;
}
```

2. 对于类组件，属性会作为一个对象的属性，传递给构造函数的参数

注意：组件的属性，应该使用小驼峰命名法

```js
import React from "react";

export default class MyClassComp extends React.Component {
  // constructor(props) {
  //     super(props); // this.props = props;
  //     console.log(props, this.props, props === this.props);
  // }

  /**
   * 该方法必须返回React元素
   */
  render() {
    if (this.props.obj) {
      return (
        <>
          <p>姓名：{this.props.obj.name}</p>
          <p>年龄：{this.props.obj.age}</p>
        </>
      );
    } else if (this.props.ui) {
      return (
        <div>
          <h1>下面是传入的内容</h1>
          {this.props.ui}
        </div>
      );
    }
    return <h1>类组件的内容，数字：{this.props.number}</h1>;
  }
}
```

```js
import React from "react";
import ReactDOM from "react-dom";
import MyFuncComp from "./MyFuncComp";
import MyClassComp from "./MyClassComp";

const comp = <MyFuncComp number={3} />; //使用组件，生成的，仍然是一个React元素，变化的，只是type值

// const div = <div title="asdasd"></div>;

ReactDOM.render(
  <div>
    <MyFuncComp number="2" />
    <MyFuncComp number={5} />
    <MyFuncComp number={6} />
    <MyFuncComp number={7} />
    <MyClassComp number="2" ennable />
    <MyClassComp
      number={5}
      obj={{
        name: "cyc",
        age: 20,
      }}
    />
    <MyClassComp number={6} ui={<h2>这是我传递属性</h2>} />
    <MyClassComp number={7} />
  </div>,
  document.getElementById("root")
);
```

**组件无法改变自身的属性**。

之前学习的 React 元素，本质上，就是一个组件（内置组件）

React 中的哲学：数据属于谁，谁才有权力改动

渲染效率：很快。React 实际上修改的是 React 对象而不是 dom 对象，所以性能开销几乎可以不计。
