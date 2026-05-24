# HTML |跑马灯循环属性

> 原文:[https://www.geeksforgeeks.org/html-marquee-loop-attribute/](https://www.geeksforgeeks.org/html-marquee-loop-attribute/)

HTML 中的**字幕循环属性**用来定义字幕应该循环的次数。循环的默认值是**无限**。
**语法:**

```html
<marquee loop="number" >
```

**属性值:**

*   **编号:**指定循环次数。

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
            font-family: "Times New Roman";
        }

        .marq {
            padding-top: 30px;
            padding-bottom: 30px;
        }

        .geek1 {
            font-size: 36px;
            font-weight: bold;
            color: white;
            text-align: center;
        }

        .geek2 {
            text-align: center;
        }
    </style>
</head>

<body>
    <div class="main">
        <marquee class="marq"
                 bgcolor="Green"
                 direction="up"
                 loop="1">

            <div class="geek1">GeeksforGeeks</div>
            <div class="geek2">
              A computer science portal for geeks
          </div>
        </marquee>
        <marquee class="marq"
                 bgcolor="Green"
                 direction="up"
                 loop="2">

            <div class="geek1">GeeksforGeeks</div>
            <div class="geek2">
              A computer science portal for geeks
          </div>
        </marquee>
    </div>
</body>

</html>
```

**输出:**

![](img/3fd1ea1a97b37166a05a7cbad9f26b37.png)

**支持的浏览器:****HTML 跑马灯循环属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧