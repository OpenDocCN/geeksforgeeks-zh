# 如何清除 ReactJS 中的完整缓存数据？

> 原文:[https://www . geesforgeks . org/how-clear-complete-cache-data-in-reactjs/](https://www.geeksforgeeks.org/how-to-clear-complete-cache-data-in-reactjs/)

我们可以在 ReactJS 中使用以下方法来清除完整的缓存数据。我们可以根据用户需求从浏览器中清除完整的缓存数据。缓存是一种技术帮助我们将给定资源的副本存储到我们的浏览器中，并在请求时提供给我们。

**方法:**按照这些简单的步骤清除 ReactJS 中的完整缓存数据。我们已经创建了我们的*清除缓存数据*功能，从浏览器中清除整个缓存数据。当我们点击按钮时，该功能被触发，整个缓存从浏览器中被删除，我们看到一个警告弹出窗口。

在下面的例子中，我们在浏览器中存储了 5 个缓存，命名为缓存一、缓存二、缓存三、缓存四和缓存五，如下所示，我们使用我们定义的函数清除了整个缓存。

![](img/046aca9d6435e3384358d8ef16e9a68a.png)

**创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

    ```jsx
    cd foldername
    ```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import * as React from 'react';

export default function App() {

  // Function to clear complete cache data
  const clearCacheData = () => {
    caches.keys().then((names) => {
      names.forEach((name) => {
        caches.delete(name);
      });
    });
    alert('Complete Cache Cleared')
  };

  return (
    <div style={{ height: 500, width: '80%' }}>
      <h4>How to clear complete cache data in ReactJS?</h4>
      <button onClick={() => clearCacheData()} >
        Clear Cache Data</button>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/3c222e3b00eba885c2c306b231cc3a75.png)