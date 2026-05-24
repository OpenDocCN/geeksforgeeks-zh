# 如何在 ReactJS 中使用芯片组件？

> 原文:[https://www . geeksforgeeks . org/如何使用芯片中的组件 reactjs/](https://www.geeksforgeeks.org/how-to-use-chip-component-in-reactjs/)

Chips 是表示输入、属性或动作的紧凑元素。【React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用以下方法在 ReactJS 中使用芯片组件。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个 React 应用程序。

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹。**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块。

```jsx
npm install @material-ui/core
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import Chip from "@material-ui/core/Chip";
import Avatar from "@material-ui/core/Avatar";

export default function App() {
  const handleClick = () => {
    alert("Clicked!!");
  };

  return (
    <div style={{ display: "block", padding: 30 }}>
      <h4>How to use Chip Component in ReactJS?</h4>
      <Chip label="Simple Basic Chip" />
      <Chip label="Disabled Chip" disabled />
      <Chip
        avatar={<Avatar>M</Avatar>}
        label="Simple Clickable Chip"
        onClick={handleClick}
      />
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序。

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。

![](img/11511792164c9e2fa87bbec50e5efff2.png)

**参考:**T2】https://material-ui.com/components/chips/