# 反应堆功能部件

> 原文:[https://www . geeksforgeeks . org/reactjs-functional-components/](https://www.geeksforgeeks.org/reactjs-functional-components/)

功能组件是在 React 中工作时会遇到的一些更常见的组件。这些只是简单的 JavaScript 函数。我们可以通过编写一个 JavaScript 函数来创建一个功能组件来进行反应。这些函数可能会也可能不会接收数据作为参数。在功能组件中，返回值是要呈现给 DOM 树的 [JSX](https://www.geeksforgeeks.org/reactjs-introduction-jsx/) 代码。
**示例:**演示功能组件创建的程序。

**文件路径- src/index.js:** 打开您的 React 项目目录，从 src 文件夹中编辑 **index.js** 文件:

## java 描述语言

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import Demo from './App';

ReactDOM.render(
  <React.StrictMode>
    <Demo />
  </React.StrictMode>,
  document.getElementById('root')
);
```

**文件路径- src/App.js:** 打开您的 React 项目目录，从 src 文件夹编辑 **App.js** 文件:

## java 描述语言

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

const Demo=()=>
{
  return <h1>Welcome to GeeksforGeeks</h1>;
}

export default Demo;
```