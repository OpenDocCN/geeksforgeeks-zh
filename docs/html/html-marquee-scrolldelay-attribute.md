# HTML |跑马灯滚动延迟属性

> 原文:[https://www . geesforgeks . org/html-marquee-scroll delay-attribute/](https://www.geeksforgeeks.org/html-marquee-scrolldelay-attribute/)

HTML 中的**选取框滚动延迟属性**用于设置每次滚动移动的间隔，单位为毫秒。Scrolldelay 的默认值是 85。
**注意:**值小于 60 不可接受，除非指定**真实速度**。
**语法:**

```html
<marquee scrolldelay=number>
```

**属性值:**

*   **编号:**定义选框速度。

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
    <div class="main">
        <marquee class="marq"
                 bgcolor="Green"
                 direction="left"
                 loop="">
            scrolldealy: default(85)
        </marquee>
        <marquee class="marq"
                 Scrolldelay=100
                 bgcolor="Green"
                 direction="left"
                 loop="">
            scrolldelay: 100
        </marquee>
    </div>
</body>

</html>
```

**输出:**

![](img/99aa0c375227d514c675f1343ab7c687.png)

**支持的浏览器:****HTML Marquee scroll delay 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧