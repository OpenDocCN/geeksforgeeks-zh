# 反应危险溶解 tinrhtml 属性

> 原文:[https://www . geeksforgeeks . org/reactjs-dangerouslystinnerhtml-attribute/](https://www.geeksforgeeks.org/reactjs-dangerouslysetinnerhtml-attribute/)

React.js 库就是将应用程序拆分成几个组件。每个组件都有自己的生命周期。React 为我们提供了一些内置的方法，我们可以在组件生命周期的特定阶段覆盖这些方法。

在基于类的组件中，dangerouslySetInnerHTML 属性用于设置页面的 InnerHTML。这是对 innerHTML 属性的替换。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个 React 应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

**项目结构**:如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from 'react';

// Defining our App Component
const App = () => {

  // Function to demonstrate dangerouslySetInnerHTML attribute
  function Set() {
    return { __html: 'Setting HTML using dangerouslySetInnerHTML attribute' };
  }

  // Returning our JSX code
  return <>
    <div>
      <h1>GeeksforGeeks</h1>
      <div
        dangerouslySetInnerHTML={Set()}></div>
    </div>
  </>;
}

// Exporting your Default App Component
export default App
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/7d0c491660840140eaab6a6dd65e9536.png)

**参考:**[https://reactjs . org/docs/DOM-elements . html # dangerouslystinnerhtml](https://reactjs.org/docs/dom-elements.html#dangerouslysetinnerhtml)