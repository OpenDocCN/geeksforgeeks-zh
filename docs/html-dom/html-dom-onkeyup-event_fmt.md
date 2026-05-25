# HTML DOM onkeyup 事件

> 原文: [https://www.geeksforgeeks.org/html-dom-onkeyup-event/](https://www.geeksforgeeks.org/html-dom-onkeyup-event/)

## 概述

HTML 中的 `DOM onkeyup` 事件发生在用户按下一个键后释放的时候。

与 `onkeyup` 事件相关的事件顺序:

1.  `onkeydown`
2.  `onkeypress`
3.  `onkeyup`

## 支持的 HTML 标签

所有 HTML 元素，除了:

*   `<iframe>`
*   `<meta>`
*   `<param>`
*   `<script>`
*   `<style>`
*   `<title>`

## 语法

*   **在 HTML 中:**
    ```html
    <element onkeyup="myScript">
    ```
*   **在 JavaScript 中:**
    ```javascript
    object.onkeyup = function(){myScript};
    ```
*   **在 JavaScript 中，使用 `addEventListener()` 方法:**
    ```javascript
    object.addEventListener("keyup", myScript);
    ```

## 示例

使用 `addEventListener()` 方法打开事件。

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML DOM onkeyup Event
        </title>
    </head>
    <body>
        <center>
            <h1 style="color:green">
                GeekforGeeks
            </h1>
            <p>
                Press any key inside the input field
            </p>
            <input type="text"
                   id="inputField"
                   style="background-color:green">
            <script>
                document.getElementById(
                    "inputField").addEventListener(
                    "keyup", GFGFun);

                function GFGFun() {
                    document.getElementById(
                        "inputField").style.backgroundColor =
                        "yellow";
                }
            </script>
        </center>
    </body>
</html>
```

**输出:**

**前:**
![img](img/9a9464954eecb8726278816caf85804e.png)

**之后:**
![img](img/d6e6cf974cc0e4114160d04f0e21ec92.png)

## 支持的浏览器

`HTML DOM onkeyup` 事件支持的浏览器如下:

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Apple Safari
*   Opera