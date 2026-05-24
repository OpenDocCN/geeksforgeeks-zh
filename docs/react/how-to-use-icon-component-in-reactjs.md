# 如何在 ReactJS 中使用图标组件？

> 原文:[https://www . geeksforgeeks . org/如何使用-icon-in-component-reactjs/](https://www.geeksforgeeks.org/how-to-use-icon-component-in-reactjs/)

为了用户界面的目的，每个应用程序都需要图标。【React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用下面的方法在 ReactJS 中使用图标组件。

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
npm install @material-ui/icons
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import DeleteIcon from "@material-ui/icons/Delete";
import Home from "@material-ui/icons/Home";
import Person from "@material-ui/icons/Person";

export default function App() {
  return (
    <div style={{ display: "block", padding: 30 }}>
      <h4>How to use Icon Component in ReactJS?</h4>
      <pre>
        Sample Delete Icon: <DeleteIcon /> <br></br>
        Sample Home Icon: <Home /> <br></br>
        Sample Person Icon: <Person /> <br></br>
      </pre>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序。

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。

![](img/09e593fba3e342b1c75945e5ab6933d4.png)

**参考**:[https://material-ui.com/components/icons/](https://material-ui.com/components/icons/)