# HTML iframe 对齐属性

> 原文:[https://www.geeksforgeeks.org/html-iframe-align-attribute/](https://www.geeksforgeeks.org/html-iframe-align-attribute/)

**HTML < iframe >对齐属性**用于根据替代元素指定内嵌框架的对齐方式。

**语法**

```html
<iframe align="left|right|middle|top|bottom">
```

**属性值**

*   **左侧:**它将 iframe 的对齐方式设置为左侧。
*   **右侧:**它将 iframe 的对齐方式设置为右侧。
*   **中间:**它将 iframe 的对齐方式设置为中间。
*   **顶部:**它将 iframe 的对齐方式设置为顶部。
*   **底部:**设置 iframe 与底部的对齐方式。

**示例:**下面的 HTML 代码演示了在< iframe >元素中使用 align 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML iframe align Attribute
    </title>

    <style>
        .left {
            text-align: left;
        }

        .right {
            text-align: right;
        }
    </style>
</head>

<body style="text-align:center;">

    <h1>GeeksforGeeks</h1>

    <h2>HTML iframe align Attribute</h2>
    <b>
        <p class="left">left-align</p>

    </b>

    <iframe align="left" src=
"https://ide.geeksforgeeks.org/index.php" 
        height="200" width="250">
    </iframe>
    <b>
        <p class="right">right-align</p>

    </b>

    <iframe align="right" src=
"https://ide.geeksforgeeks.org/index.php" 
        height="200" width="250">
    </iframe>
</body>

</html>
```

**输出:**

![](img/f5d5a3d9b6ee987ec06a8f4ae71ef80d.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   歌剧
*   苹果 Safari
*   火狐浏览器