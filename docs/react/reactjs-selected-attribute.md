# 重新选择属性

> 原文:[https://www.geeksforgeeks.org/reactjs-selected-attribute/](https://www.geeksforgeeks.org/reactjs-selected-attribute/)

React.js 库就是将应用程序拆分成几个组件。每个组件都有自己的生命周期。React 为我们提供了一些内置的方法，我们可以在组件生命周期的特定阶段覆盖这些方法。

在本文中，我们将了解如何使用选定的属性。所选属性用于设置已显示在选择元素上的默认选定选项。

**创建反应应用程序并安装模块:**

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

**示例:**

## App.js

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import ReactDOMServer from 'react-dom/server';

const element = <div>
    <h1>GeeksforGeeks</h1>
    <select>
      <option value="React">React</option>
      <option value="Angular">Angular</option>
      <option selected value="JavaScript">JavaScript</option>
      <option value="HTML">HTML</option>
    </select>
</div>;

ReactDOM.render(
  element,
    document.getElementById("root")
);
```

**输出:**

![](img/63e49937c4ed546579f0938ac584774d.png)

**参考:**T2】https://reactjs.org/docs/dom-elements.html#selected