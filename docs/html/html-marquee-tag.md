# HTML marquee 标签

> 原文:[https://www.geeksforgeeks.org/html-marquee-tag/](https://www.geeksforgeeks.org/html-marquee-tag/)

HTML 中的<marquee>标签用于在网页中创建滚动文本或图像。它可以水平地从左向右或从右向左滚动，也可以垂直地从上到下或从下到上滚动。</marquee>

**语法:**

字幕元素成对出现。这意味着标签有开始和结束元素。

```html
<marquee>
 <--- contents --->
</marquee> 
```

**属性**

<figure class="table">

| 属性 | 价值观念 | 描述 |
| --- | --- | --- |
| bgcolor(bgcolor) | 颜色名称 | 定义字幕的背景颜色。 |
| 方向 | 上、下、左、右 | 定义滚动内容的方向 |
| 环 | 数字 | 指定内容移动的次数。默认值为无穷大。 |
| 高度 | px 或% | 定义字幕的高度 |
| 宽度 | px 或% | 定义字幕的宽度 |
| hspace | 像素 | 指定字幕周围的水平间距 |
| vspace | 像素 | 指定选取框周围的垂直间距 |

</figure>

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Marquee Tag</title>
    <style>
    .main {
        text-align:center;
    }
    .marq {
        padding-top:30px;
        padding-bottom:30px;
    }
    .geek1 {
        font-size:36px;
        font-weight:bold;
        color:white;
        padding-bottom:10px;
    }
    </style>
</head>

<body>
    <div class = "main">
    <marquee class="marq" bgcolor = "Green" direction = "left" loop="" >
        <div class="geek1">GeeksforGeeks</div>
        <div class="geek2">A computer science portal for geeks</div>
    </marquee>
    </div>
</body>
</html>                   
```

**输出:**
选框标签

GeeksforGeeksA computer science portal for geeks 

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Marquee Tag</title>
    <style>
    .main {
        text-align:center;
        font-family:"Times New Roman";
    }
    .marq {
        padding-top:30px;
        padding-bottom:30px;
    }
    .geek1 {
        font-size:36px;
        font-weight:bold;
        color:white;
        text-align:center;
    }
    .geek2 {
        text-align:center;
    }
    </style>
</head>

<body>
    <div class = "main">
    <marquee class="marq" bgcolor = "Green" direction = "up" loop="" >
        <div class="geek1">GeeksforGeeks</div>
        <div class="geek2">A computer science portal for geeks</div>
    </marquee>
    </div>
</body>
</html>                   
```

**输出:**
选框标签

GeeksforGeeksA computer science portal for geeks 

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Marquee Tag</title>
    <style>
    .main {
        text-align:center;
        font-family:"Times New Roman";
    }
    .marq {
        padding-top:30px;
        padding-bottom:30px;
    }
    .geek1 {
        font-size:36px;
        font-weight:bold;
        color:white;
        text-align:center;
    }
    .geek2 {
        text-align:center;
    }
    </style>
</head>

<body>
    <div class = "main">
    <marquee class="marq" bgcolor = "Green" direction = "down" loop="" >
        <div class="geek1">GeeksforGeeks</div>
        <div class="geek2">A computer science portal for geeks</div>
    </marquee>
    </div>
</body>
</html>                   
```

**输出:**
选框标签

GeeksforGeeksA computer science portal for geeks 

**支持的浏览器**

*   谷歌 Chrome 1.0
*   Edge 12.0
*   Firefox 65.0
*   Internet Explorer 2.0
*   歌剧 7.2
*   Safari 1.2