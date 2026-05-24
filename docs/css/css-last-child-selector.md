# CSS |:末子选择器

> 原文:[https://www.geeksforgeeks.org/css-last-child-selector/](https://www.geeksforgeeks.org/css-last-child-selector/)

**:最后一个子元素选择器**用于针对其父元素的最后一个子元素进行造型。该选择器与“第 n 个-最后一个-子”相同。

**语法:**

```html
:last-child {
  //property
}

```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        p:last-child {
            background: limegreen;
            color: white;
            font-style: italic;
            font-size: 1.875em;
        }
    </style>
</head>

<body>

    <p>I am first child.</p>
    <p>I am second child.</p>
    <p>I am third child.</p>
    <p>I am last child.</p>

</body>

</html>
```

**输出:**
![](img/21306e72b7a5910b400f41aeb7e7aa66.png)

**支持的浏览器:**

*   谷歌 Chrome 4.0
*   Edge 9.0
*   Firefox 3.5
*   Safari 3.2
*   歌剧 9.6