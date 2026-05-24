# HTML |使用地图属性

> 原文:[https://www.geeksforgeeks.org/html-usemap-attribute/](https://www.geeksforgeeks.org/html-usemap-attribute/)

**HTML usemap 属性**用于将图像/对象指定为图像地图。它与地图元素的名称或 id 属性相关，并在 **img** 和**地图**之间创建关系。

**支持的标签:**

*   [img](https://www.geeksforgeeks.org/html-img-usemap-attribute/)
*   [物体](https://www.geeksforgeeks.org/html-object-usemap-attribute/?ref=rp)

**语法**

```html
<element_name usemap="#mapname">
```

**属性值:**

*   **映射名:**用于保存包含哈希(#)字符的映射名。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML img usemap Attribute</title>

    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML <img> usemap Attribute</h2>

    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165729/area11.png"
        alt="" width="300" height="119" usemap="#shapemap" />

    <map name="shapemap">

        <!-- area tag contained image. -->
        <area shape="poly" coords="59, 31, 28, 83, 91, 83" href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165802/area2.png"
            alt="Triangle">

        <area shape="circle" coords="155, 56, 26" href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165934/area3.png"
            alt="Circle">

        <area shape="rect" coords="224, 30, 276, 82" href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227170021/area4.png"
            alt="Square">
    </map>
</body>

</html>
```

**输出:**

![](img/aed4b7ee6132833c8dc8ec8b00eb2298.png)

**支持的浏览器:****HTML usemap 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧