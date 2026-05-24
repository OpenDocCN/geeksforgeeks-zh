# 如何在 ReactJS 中创建打字机效果？

> 原文:[https://www . geeksforgeeks . org/如何创建打字机效果 in-reactjs/](https://www.geeksforgeeks.org/how-to-create-typewriter-effect-in-reactjs/)

[ReactJS](https://www.geeksforgeeks.org/reactjs/) 中的打字机效果是一个 JS 包，可以用于更好的 UI 设计。这个效果让我们可以在 ReactJS 中创建一个简单的打字动画。为了在 ReactJS 中使用打字机，我们需要安装打字机效果包。

**先决条件:**

*   ReactJS 基础知识
*   已创建 ReactJSapp

下面按顺序描述了在 React 中使用样式化组件的所有步骤。

**安装:**

*   **第一步:**在继续之前，首先我们必须安装打字机效果，通过在项目目录中运行以下命令，借助 src 文件夹中的终端，或者您也可以在项目文件夹中的 Visual Studio Code 终端中运行该命令。

    ```jsx
    npm install --save typewriter-effect
    ```

    ```jsx
    yarn add typewriter-effect
    ```

*   **步骤 2:** 安装完包后，现在打开项目目录中 src 文件夹下的 App.js 文件，并删除其中的代码。
*   **第三步:**现在导入 React 和打字机效果包。
*   **第四步:**在你的 app.js 文件中，添加这个代码片段来导入 React 和打字机效果包。

    ```jsx
    import React from 'react';
    import Typewriter from "typewriter-effect";
    ```

下面是一个演示打字机效果的示例程序:

**文件名- App.js:**

## java 描述语言

```jsx
import React from 'react';

//importing typewriter-effect
import Typewriter from "typewriter-effect";
import './App.css';

function App() {
  return (
    <div className="App">
      <Typewriter

       onInit={(typewriter)=> {

       typewriter

       .typeString("GeeksForGeeks")

       .pauseFor(1000)
       .deleteAll()
       .typeString("Welcomes You")
       .start();
       }}
       />
    </div>
  );
}

export default App;
```

**文件名- 应用程序.css**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```jsx
.App {
  font-family: sans-serif;
  font-weight:800;
  font-size:40px;
  text-align: center;
  display:flex;
  justify-content:center;
  align-items:center;
  min-height:100vh;
  background:green;
}
```

**输出:**因此使用上述步骤，我们可以使用打字机效果来导入和更改打字动画[反应](https://www.geeksforgeeks.org/reactjs/)。

![](img/944e20be540bd4d61127ea21b29a6e9f.png)