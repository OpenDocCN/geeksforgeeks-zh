# 如何在 ReactJS 中使用 AvatarGroup 组件？

> 原文:[https://www . geeksforgeeks . org/how-用法-avatar group-component-in-reactjs/](https://www.geeksforgeeks.org/how-to-use-avatargroup-component-in-reactjs/)

AvatarGroup 组件用于将头像的多个组合在一起。它将其子级呈现为堆栈。【React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用以下方法在 ReactJS 中使用 AvatarGroup 组件。

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
npm install @material-ui/lab
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import AvatarGroup from "@material-ui/lab/AvatarGroup";
import Avatar from "@material-ui/core/Avatar";

export default function App() {
  return (
    <div style={{ display: "block" }}>
      <h4>How to use AvatarGroup Component in ReactJS?</h4>
      <AvatarGroup max={4}>
        <Avatar alt="Geeksforgeeks" src="YourPicturePath" />
        <Avatar alt="Random Name" src="YourPicturePath" />
        <Avatar alt="Unknow" src="YourPicturePath" />
        <Avatar alt="Gourav" src="YourPicturePath" />
        <Avatar alt="Harrier" src="YourPicturePath" />
      </AvatarGroup>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序。

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。

![](img/a0b7c4b2b6264d62916f5758ae7c3c9a.png)

**参考:**T2】https://material-ui.com/components/avatars/#grouped