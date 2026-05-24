# 重新获取吐司通知

> 原文:[https://www.geeksforgeeks.org/reactjs-toast-notification/](https://www.geeksforgeeks.org/reactjs-toast-notification/)

**吐司通知**是为了向用户显示消息而添加的弹出消息。它可以是成功消息、警告消息或自定义消息。敬酒通知也叫**敬酒通知**。这个所有敬酒通知都在反应不足模块中，所以要使用它们，我们需要导入这个模块。
**先决条件:**

*   [ReactJS 基础知识](https://www.geeksforgeeks.org/reactjs/)
*   **NodeJS:**
    *   [在 Windows 上安装 node . js](https://www.geeksforgeeks.org/installation-of-node-js-on-windows/)
    *   [在 Linux 上安装 node . js](https://www.geeksforgeeks.org/installation-of-node-js-on-linux/)
*   [已创建 ReactJS 应用程序](https://www.geeksforgeeks.org/reactjs-setting-development-environment/)

下面按顺序描述了添加吐司通知的所有步骤及其配置。

*   **第 1 步:**在继续之前，首先我们必须安装 react-toastify 模块，通过在项目目录中运行以下命令，借助 src 文件夹中的终端，或者您也可以在项目文件夹中的 Visual Studio Code 的终端中运行该命令。

```jsx
npm add react-toastify
```

*   **第二步:**安装完 react-toastify 模块后，现在打开您的 **app.js** 文件，该文件位于您的项目目录中的 src 文件夹下，并删除其中预设的代码。
*   **第三步:**现在导入 react-toasty 模块，toastify CSS 文件，以及一个 toast 通知的调用者方法。
*   **第四步:**在你的 **app.js** 文件中，通过在你的 **app.js**
    中添加下面的代码，添加这个代码来导入烤面包机模块

```jsx
import {toast} from 'react-toastify';
import 'react-toastify/dist/ReactToastify.css';
toast.configure()
```

**例 1:** 默认通知位置为右上角。

*   **app.js:**

## java 描述语言

```jsx
import React from 'react';

// Importing toastify module
import {toast} from 'react-toastify';

// Import toastify css file
import 'react-toastify/dist/ReactToastify.css';

 // toast-configuration method,
 // it is compulsory method.
toast.configure()

// This is main function
function GeeksforGeeks(){
    // function which is called when
    // button is clicked
    const notify = ()=>{

        // Calling toast method by passing string
        toast('Hello Geeks')
    }
    return (
        <div className="GeeksforGeeks">
            <button onClick={notify}>Click Me!</button>
            </div>
    );
}

export default GeeksforGeeks;
```