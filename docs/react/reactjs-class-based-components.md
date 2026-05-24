# 基于 ReactJS 类的组件

> 原文:[https://www . geeksforgeeks . org/reactjs-基于类的组件/](https://www.geeksforgeeks.org/reactjs-class-based-components/)

React **基于类的组件**是大多数内置于 ReactJS 中的现代网络应用的基础。这些组件是简单的类(由向应用程序添加功能的多个函数组成)。所有基于**类的组件**都是 ReactJS 的组件类的子类。

**示例:**演示基于类的组件创建的程序。创建一个反应应用程序，并将**应用程序编辑为:**

**文件名- App.js:**

## java 描述语言

```jsx
import React from "react";

class App extends React.Component {
  render() {
    return <h1>GeeksForGeeks</h1>;
  }
}

export default App;
```