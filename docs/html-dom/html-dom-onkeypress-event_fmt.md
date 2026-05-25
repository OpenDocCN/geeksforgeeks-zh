# HTML DOM onkeypress 事件

> 原文: [https://www.geeksforgeeks.org/html-dom-onkeypress-event/](https://www.geeksforgeeks.org/html-dom-onkeypress-event/)

HTML 中的 `DOM onkeypress` 事件发生在用户按下某个键时。

与 `onkeypress` 事件相关的事件顺序:

*   `onkeydown`
*   `onkeypress`
*   `onkeyup`

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
    <element onkeypress="myScript">
    ```
*   **在 JavaScript 中:**
    ```javascript
    object.onkeypress = function(){myScript};
    ```
*   **在 JavaScript 中，使用 `addEventListener()` 方法:**
    ```javascript
    object.addEventListener("keypress", myScript);
    ```

## 示例

使用 `addEventListener()` 方法在按键事件上

```html
<!DOCTYPE html>
<html>
   <head>
       <title>
          DOM onkeypress event
       </title>
   </head>
   <body>
       <center>
           <h1 style="color:green">
              GeekforGeeks
           </h1>
           <p>Press any key inside the input field</p>
           <input type="text"
                  id="inputField"
                  style="background-color:green">
           <script>
               document.getElementById(
                 "inputField").addEventListener("keypress", GFGFun);
               function GFGFun() {
                   document.getElementById(
                     "inputField").style.backgroundColor = "yellow";
               }
           </script>
       </center>
   </body>
</html>
```

## 输出

**前:**
![img](img/9a9464954eecb8726278816caf85804e.png)

**后:**
![img](img/d6e6cf974cc0e4114160d04f0e21ec92.png)

## 支持的浏览器

`onkeypress` 事件上 HTML DOM 支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧