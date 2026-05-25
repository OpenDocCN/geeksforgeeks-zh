# HTML | DOM onscroll 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onscroll-event/](https://www.geeksforgeeks.org/html-dom-onscroll-event/)

当使用滚动条时，会发生滚动事件。CSS 溢出用于创建滚动条。

## 支持的标签

*   `<body>`
*   `<iframe>`
*   `<marquee>`
*   `<div>`
*   `<article>`
*   `<aside>`
*   `<footer>`
*   `<header>`
*   `<nav>`
*   `<section>`
*   `<details>`
*   `<figcaption>`
*   `<figure>`
*   `<main>`
*   `<p>`
*   `<pre>`
*   `<ol>`
*   `<ul>`
*   `<li>`
*   `<tfoot>`
*   `<thead>`
*   `<textarea>`
*   `<select>`
*   `<object>`

## 语法

**在 HTML 中:**
```html
<element onscroll="myScript">
```

**在 JavaScript 中:**
```javascript
object.onscroll = function(){myScript};
```

**在 JavaScript 中，使用 `addEventListener()` 方法:**
```javascript
object.addEventListener("scroll", myScript);
```

## 示例

使用 `addEventListener()` 方法

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML DOM onscroll Event</title>
</head>
<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>
        <h2>HTML DOM onscroll Event</h2>
        <textarea style="width:100%" id="tID">
            HTML stands for Hyper Text Markup Language.
            It is used to design web pages using markup language.
            HTML is the combination of Hypertext and Markup language.
            Hypertext defines the link between the web pages.
            Markup language is used to define the text document
            within tag which defines the structure of web pages.
            HTML is a markup language which is used by the browser
            to manipulate text, images and other content to
            display it in required format.
        </textarea>
        <p id="try"></p>
    </center>
    <script>
        document.getElementById("tID").addEventListener("scroll", GFGfun);

        function GFGfun() {
            document.getElementById("try").innerHTML = "Textarea scrolled.";
        }
    </script>
</body>
</html>
```

**输出:**

![img](img/49e1769d60767c57e29828a775a4c58f.png)

## 支持的浏览器

**HTML DOM onscroll 事件**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧