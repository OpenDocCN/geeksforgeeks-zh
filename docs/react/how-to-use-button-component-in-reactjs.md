# 如何在 ReactJS 中使用按钮组件？

> 原文:[https://www . geeksforgeeks . org/how-to-use-button-in-component-reactjs/](https://www.geeksforgeeks.org/how-to-use-button-component-in-reactjs/)

**按钮**允许用户通过一次点击来采取行动和做出选择。React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用以下方法在 ReactJS 中使用**按钮**组件。

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
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import React from 'react';
import Button from '@material-ui/core/Button';

const App = () => {

  return (
    <div style={{
      display: 'flex',
      margin: 'auto',
      width: 400,
      flexWrap: 'wrap',
    }}>
      <div style={{ width: '100%', float: 'left' }}>
        <h3>How to use Button Component in ReactJS?</h3> <br />
      </div>
      <Button variant="contained">Default Button</Button>
      <Button variant="contained" color="primary">
        Primary Button
      </Button>
      <Button variant="contained" color="secondary">
        Secondary Button
      </Button>
      <Button variant="contained" disabled>
        Disabled Button
      </Button>
      <Button variant="contained" color="primary"
        href="#">
        Link Button
      </Button>
    </div>
  );
}

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/221bb26d959e2c23cf434457f604f8a3.png)