# 如何在 ReactJS 中串联 unicode 和变量？

> 原文:[https://www . geeksforgeeks . org/如何在 reactjs 中连接 unicode 和变量/](https://www.geeksforgeeks.org/how-to-concatenate-unicode-and-variable-in-reactjs/)

**Unicode:** Unicode 是宇宙中所有字符的编码标准。这个世界上的每一种语言代码和符号都是由 Unicode 指定的。没有支持所有语言的编码标准，通过使用 Unicode 标准，我们可以检索和组合所有语言组合的数据。

**示例:**

![](img/f0ffdd6eb485d4bd7e30026b1b491a73.png)

U+2192

在上面的例子中，一个向右的箭头用 Unicode 表示为 U+2192。

**如何创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个 React 应用程序。

    ```jsx
     npx create-react-app geeksforgeeks
    ```

*   **步骤 2:** 创建项目文件夹(即 geeksforgeeks)后，使用以下命令移动到该文件夹。

    ```jsx
    cd geeksforgeeks
    ```

    **项目结构:**

    ![](img/3dc940ea0051cffa92241a967a61de3a.png)

    **文件夹结构**

    **如何在 ReactJS 中连接 Unicode 和变量:**为了连接，我们首先将 Unicode 转换为它的数值，为此，我们将使用 parseInt。

    ```jsx
    parseInt(Unicode,base)
    ```

    现在，这个数值需要转换成它的字符，为此，我们可以使用

    ```jsx
    String.fromCodePoint(numericalValue).
    ```

    **示例:**对 App.js 文件进行以下更改

    ## App.js

    ```jsx
    import React from 'react'
        const App = ({ unicode }) => {

        return(

           <h1>
               This is a Right arrow
               {String.fromCodePoint(parseInt(unicode,16))}
           </h1>
       )}
    export default App;
    ```

    现在在您的 index.js 文件中导入这个 App.js 文件(默认情况下，它已经被导入)，并在 App 组件中传递 Unicode 值。

    ## index.js

    ```jsx
    import React from 'react';
    import ReactDOM from 'react-dom';
    import App from './App';

        ReactDOM.render(
        <React.StrictMode>
           <App unicode='2192'/>
        </React.StrictMode>,

       document.getElementById('root')

        );
    ```

    现在在 react-app 目录中使用以下命令运行本地服务器

    ```jsx
    npm start
    ```

    **输出:**

    ![](img/463376f38d7bed92f67944b835d3c272.png)