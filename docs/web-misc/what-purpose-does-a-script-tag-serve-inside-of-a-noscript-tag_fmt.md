# `<noscript>` 标签中 `<script>` 标签的作用是什么？

> 原文：<https://www.geeksforgeks.org/what-purpose-does-a-script-tag-serve-in-a-noscript-tag/>

`<script>` 标签既可用于 `<head>` 和 `<body>` 标签。

**语法：**
```html
<noscript>目录</noscript>
```

**示例：**
```html
<html>
    <head>
        <title>wbr 标签</title>
        <style>
            body {
                text-align: center;
            }
            .gfg {
                font-size: 40px;
                font-weight: bold;
                color: green;
            }
            .geek {
                font-size: 25px;
                font-weight: bold;
            }
        </style>
    </head>
    <body>
        <div class="gfg">geeksforgeeks</div>
        <div class="geek">
            <code><noscript></code>标签
        </div>
        <script>
            document.write("Geeks!")
        </script>
        <noscript>计算机科学门户</noscript>
    </body>
</html>
```

**输出：**
![img/df75413516c0fcdf701f13d625ffac57.png](img/df75413516c0fcdf701f13d625ffac57.png)