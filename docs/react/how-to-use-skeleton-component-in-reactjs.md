# 如何在 ReactJS 中使用骨骼组件？

> 原文:[https://www . geeksforgeeks . org/如何使用骨架组件 in-reactjs/](https://www.geeksforgeeks.org/how-to-use-skeleton-component-in-reactjs/)

每当数据为**未加载**时，使用**骨架**组件，占位符预览将显示给用户。该组件显示我们内容的占位符预览。**React 的 Material UI** 有这个组件可供我们使用，非常容易集成。我们可以在 ReactJS 中使用以下方法来使用骨架组件。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块:

```jsx
npm install @material-ui/core
npm install @material-ui/lab
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import Skeleton from "@material-ui/lab/Skeleton";

export default function App() {
  return (
    <div style={{ display: "block", padding: 30 }}>
      <h4>How to use Skeleton Component in ReactJS?</h4>
      TEXT VARIANT: <Skeleton variant="text" width={200} />
       <br />
      RECTANGULAR VARIANT: <Skeleton
        variant="rect"
        width={110}
        height={220}
      />{" "}
       <br />
      CIRCLE VARIANT: 
        <Skeleton variant="circle"
                  width={50} height={50} />{" "}
      <br />
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/ef6600bd000578900a21091da8dd8e11.png)

**参考:**T2】https://material-ui.com/components/skeleton/