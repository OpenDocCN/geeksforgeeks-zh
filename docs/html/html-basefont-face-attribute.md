# HTML | <basefont>人脸属性

> 原文:[https://www.geeksforgeeks.org/html-basefont-face-attribute/](https://www.geeksforgeeks.org/html-basefont-face-attribute/)

**HTML 人脸属性**用于指定文档的默认字体样式。
**语法:**

```html
<basefont face="font_family">
```

**属性值:**包含值 **font_Family** ，指定文档中文本使用的各种字体样式。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      basefont face Attribute
  </title>
    <basefont color="red"
              size="9"
              face="courier, serif">
    <style>
        body {
            text-align: center;
        }

        .gfg {
            font-size: 40px;
            font-weight: bold;
            color: green;
        }

        .geeks {
            font-size: 25px;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <div class="gfg">
      GeeksforGeeks
  </div>
    <div class="geeks">
      HTML basefont face Attribute
  </div>

<p>
      A computer science portal for geeks
  </p>

</body>

</html>
```

**输出:**

![](img/4eb6517ac7e6c2a1b905a6a7f658a95e.png)

**支持的浏览器:**基于字体>人脸属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧