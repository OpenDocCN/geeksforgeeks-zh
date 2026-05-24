# 如何导入 HTML 格式的谷歌字体？

> 原文:[https://www . geesforgeks . org/如何导入-Google-font-in-html/](https://www.geeksforgeeks.org/how-to-import-google-fonts-in-html/)

为网页选择合适的字体是任何设计的一个非常重要的方面。使用网络字体服务，您可以使用多种字体来呈现网页中的数据。谷歌字体是一个免费的网络字体服务，有大量的字体可供选择。我们可以在网页中使用这些字体。

要使用自定义字体，我们需要从网络字体服务谷歌字体中导入字体系列。

**方法-1:** 使用 *<链接>* 标签

> <link href="’https://fonts.googleapis.com/css?family=Sofia’" rel="’stylesheet’/">

**方法-2:** 使用*@导入*规则

> @ import URL(' https://fonts . googleapi . com/CSS？family = Poppins’)；

**示例-1:**

```html
<html>

<head>
    <link href=
'https://fonts.googleapis.com/css?family=Sofia' 
          rel='stylesheet' />
    <style>
        h1 {
            font-family: Sofia;
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
    </center>
</body>

</html>
```

**输出:**
![](img/f5370059e09f8a12c19f708387a1a1b0.png)
**例:**

```html
<html>

<head>
    <style>
        @import url(
         https://fonts.googleapis.com/css?family=Open+Sans);
        h1 {
            font-family: 'Open Sans', serif;
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>
GeeksforGeeks</h1>
    </center>
</body>

</html>
```

**输出:**
![](img/e1ce308df69f01a3ebb3562d22b8b090.png)