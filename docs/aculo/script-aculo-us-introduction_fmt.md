# script.aculo.us 简介

> 原文:[https://www.geeksforgeeks.org/script-aculo-us-introduction/](https://www.geeksforgeeks.org/script-aculo-us-introduction/)

`script.aculo.us` 可以用来增强 GUI，给用户 Web 2.0 体验。`script.aculo.us` 允许我们通过文档对象模型在网络中添加动态视觉效果和用户界面。这是一个建立在原型 JavaScript 框架之上的 JavaScript 库。

## 下载 script.aculo.us

*   从 `script.aculo.us` [下载页面](http://script.aculo.us/downloads)下载 `scriptaculous.zip` 包。
*   解压该包，并将以下文件从 *src* 和 *lib* 文件夹复制到你的网站文件夹（这里，我们将目标文件夹命名为'JavaScript'）：
    *   `builder.js`
    *   `controls.js`
    *   `effects.js`
    *   `scriptaculous.js`
*   `prototype.js`

## 在你的代码中使用

```html
<!DOCTYPE html>
<html>

<head>
    <script 
        src="/javascript/prototype.js">
    </script>

    <script 
        src="/javascript/scriptaculous.js">
    </script>
</head>

<body>
    <h2>Welcome To GFG</h2>

    <p>
        Default code has been loaded 
        into the Editor.
    </p>
</body>

</html>
```

默认情况下，包含 `scriptaculous.js` 会包含所有可用的效果。但是如果你想只包含一些效果，你可以用下面的代码来指定：

```html
<script src="/javascript/scriptaculous.js?load=effects,dragdrop"></script>
```