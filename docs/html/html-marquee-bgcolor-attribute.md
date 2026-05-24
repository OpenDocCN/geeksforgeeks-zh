# HTML | Marquee bgcolor 属性

> 原文:[https://www . geesforgeks . org/html-marquee-bgcolor-attribute/](https://www.geeksforgeeks.org/html-marquee-bgcolor-attribute/)

HTML 中的**字幕 bgcolor 属性**用于设置字幕的背景颜色。
**语法:**

```html
<marquee bgcolor="colorname" >
```

**属性值:**

*   **颜色名称:**定义选框的背景颜色。
*   **十六进制数**:指定文档中背景颜色的十六进制编码。
*   r **gb_number:** 指定文档中背景颜色的 rgb 值

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

        .marq {
            padding-top: 30px;
            padding-bottom: 30px;
        }
    </style>
</head>

<body>
    <h1 style="color:green; text-align:center;">
      GeeksforGeeks
  </h1>

    <marquee class="marq"
             bgcolor="Green"
             direction="left"
             loop="">
        Background color is green
    </marquee>

</body>

</html>
```

**输出:**

![](img/f5f1794fb3efb4884d61f0c16a56f401.png)

**支持的浏览器:****HTML Marquee bgcolor 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧