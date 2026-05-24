# HTML |字幕宽度属性

> 原文:[https://www.geeksforgeeks.org/html-marquee-width-attribute/](https://www.geeksforgeeks.org/html-marquee-width-attribute/)

HTML 中的 [**【选取框】**](https://www.geeksforgeeks.org/html-marquee-tag/) **宽度属性**用于设置选取框的宽度，单位为像素或百分比值。
**语法:**

```html
<marquee width="px/%" >
```

**属性值:**

*   **px:** 定义选框的宽度值。
*   **%:** 定义字幕的宽度值。

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Marquee Tag</title>
    <style>
        .main {
            text-align: center;
        }
    </style>
</head>

<body>
    <h1 style="color:green; text-align:center;">
      GeeksforGeeks
  </h1>
    <div class="main">
        <marquee width=25px
                 bgcolor="Green"
                 direction="left"
                 loop="">
            Left
        </marquee>
        <br>
        <marquee width=50px
                 bgcolor="Green"
                 direction="right"
                 loop="">
            Right
        </marquee>
        <br>
        <marquee width=75px
                 bgcolor="Green"
                 direction="left"
                 loop="">
            Left
        </marquee>
        <br>
        <marquee width=100px
                 bgcolor="Green"
                 direction="right"
                 loop="">
            Right
        </marquee>
        <br>
        <marquee width=125px
                 bgcolor="Green"
                 direction="left"
                 loop="">
            Left
        </marquee>
        <br>
        <marquee width=150px
                 bgcolor="Green"
                 direction="right"
                 loop="">
            Right
        </marquee>
    </div>
</body>

</html>
```

**输出:**

![](img/dfb3c8e87b1d9f73133bd64f31c1f217.png)

**支持的浏览器:****HTML 字幕宽度属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧