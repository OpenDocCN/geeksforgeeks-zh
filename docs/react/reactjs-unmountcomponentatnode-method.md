# 重新获取卸载组件节点()方法

> 原文:[https://www . geeksforgeeks . org/reactjs-unmontcomponentatnode-method/](https://www.geeksforgeeks.org/reactjs-unmountcomponentatnode-method/)

React.js 库就是将应用程序拆分成几个组件。每个组件都有自己的生命周期。React 为我们提供了一些内置的方法，我们可以在组件生命周期的特定阶段覆盖这些方法。

在基于类的组件中，unmountComponentAtNode()方法从 DOM 中移除已装载的 React 组件。

**创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个 React 应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from 'react'
import ReactDOM from 'react-dom';

// Exporting your App Component
export default function App() {

  // Function to unmount root component
  function unm() {
    ReactDOM.unmountComponentAtNode(document.getElementById("root"));
  }

  return (
    <div>
      <h1>GeeksforGeeks</h1>
      <div>Hi Geek, this is the rendered content</div>
      <button onClick={unm}>Unmount</button>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/526275ceeef5c306b333440377a7290e.png)

**参考:**[https://reactjs . org/docs/react-DOM . html # unmontcomponentatnode](https://reactjs.org/docs/react-dom.html#unmountcomponentatnode)