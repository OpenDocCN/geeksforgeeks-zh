# HTML | <input> alt 属性

> 原文:[https://www.geeksforgeeks.org/html-input-alt-attribute/](https://www.geeksforgeeks.org/html-input-alt-attribute/)

**HTML <输入> alt 属性**用于*在图像属性未显示时为图像指定替代文本*。当图像未被加载显示时，它为用户提供替代信息。

**语法:**

```html
<input alt="text">
```

**属性值:**包含单值文本，用于在图像未显示时指定输入的替代文本。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Input alt Attribute
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>HTML Input alt Attribute</h2>
    <input id="myImage"
           type="image" 
           src=
"https://media.geeksforgeeks.org/wp-content/uploads/gfg-40.png"
           alt="Submit"
           width="48"
           height="48">
</body>

</html>
```

**输出:**
![](img/823891f8ca861e310e0a8008ccb7f224.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   边缘
*   歌剧
*   苹果 Safari