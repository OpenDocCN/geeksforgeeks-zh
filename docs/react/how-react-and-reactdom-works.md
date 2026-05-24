# 【React 和 ReactDOM 是如何工作的？

> 原文:[https://www.geeksforgeeks.org/how-react-and-reactdom-works/](https://www.geeksforgeeks.org/how-react-and-reactdom-works/)

当你与 React 合作时，你很可能会与 JSX 一起开发你的应用程序。JSX 是一个基于标签的 JavaScript 语法，看起来很熟悉 HTML。反应元素是原子，也是最基本的单位，你需要在 JSX 之前掌握它，然后才能使用反应。

**注意:**为了在浏览器中使用 React，我们需要包含两个库:React 和 ReactDOM。React 库负责创建视图，ReactDOM 库负责在浏览器中实际呈现 UI。

**包括脚本:**以下是 React 和 ReactDOM 的 CDN 链接:

```jsx
React: https://cdnjs.com/libraries/react
ReactDOM: https://cdnjs.com/libraries/react-dom
```

在您的主 JavaScript 文件之前包含这两个库。在学习 react 如何工作的同时，我们将使用 React 和 ReactDOM 构建一个小应用程序。为了简单起见，它在同一个文件夹中只包含 2 个文件***【index.html】***和 ***main.js*** 。您应该使用 React 开发版本在浏览器控制台中获取错误消息和警告。

## HTML

```jsx
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>React | How React works</title>
</head>
<body>
  <script crossorigin src=
"https://unpkg.com/react@17/umd/react.development.js">
  </script>
  <script crossorigin src=
"https://unpkg.com/react-dom@17/umd/react-dom.development.js">
  </script>
  <script src="./main.js"></script>
</body>
</html>
```