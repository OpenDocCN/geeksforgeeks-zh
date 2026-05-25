# 如何用 JavaScript 创建弹出打印对话框？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-pop-up-to-print-dialog-box-using-javascript/](https://www.geeksforgeeks.org/how-to-create-a-pop-up-to-print-dialog-box-using-javascript/)

给定一个 HTML 文档，任务是设计一个按钮，弹出一个打印对话框。我们将使用 JavaScript 来完成分配的任务:

## 方法一

*   **Approach:**
    *   添加一个链接到 JavaScript 函数的按钮。
    *   在 JavaScript 函数中，使用 JavaScript 默认函数调用打印对话框。

**语法:**

```
window.print
```

**示例:**

```
<!DOCTYPE html>
<html>
<head>
    <title>create a pop-up to print dialog box using JavaScript</title>
</head>
<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>
        <script>
            function printPopUp() {
                alert("Pop-up dialog-box")
                window.print();
            }
        </script>
        <button onclick="printPopUp()">Print</button>
    </center>
</body>
</html>
```

**输出:**
**前:**
![](img/b1b1bf9d11d9bfc5ade669e267115a6e.png)
**后:**
![](img/17cecce9ff92b9143cbe5e27796fd414.png)

## 方法二

*   **Approach:**
    *   在 `body` 标签中使用 `onload` 事件。
    *   使用弹出对话框和 `window` 的 `alert()` 方法，以及 `window.print()` 打印文档。

**示例:**

```
<!DOCTYPE html>
<html>
<head>
    <title>create a pop-up to print dialog box using JavaScript</title>
</head>
<body onload="alert('Pop-up dialog-box');window.print();">
    <center>
        <h1 style="color:green">
            GeeksforGeeks
        </h1>
        create a pop-up to print dialog box using JavaScript
    </center>
</body>
</html>
```

**输出:**
![](img/17cecce9ff92b9143cbe5e27796fd414.png)

## 方法三

*   **Approach:**
    *   使用 `href` 属性为 `javascript:` 伪协议的链接。
    *   使用弹出对话框和 `window` 的 `alert()` 方法，以及 `window.print()` 打印文档。

**示例:**

```
<!DOCTYPE html>
<html>
<head>
    <title>create a pop-up to print dialog box using JavaScript</title>
</head>
<body>
    <center>
        <h1 style="color:green">
            GeeksforGeeks
        </h1>
        <a href="javascript:alert('Pop-up dialog-box');window.print();">
            Click Me
        </a>
    </center>
</body>
</html>
```

**输出:**
**前:**
![](img/d3708290e3ce1926e375d80ed72285dc.png)
**之后:**
![](img/17cecce9ff92b9143cbe5e27796fd414.png)