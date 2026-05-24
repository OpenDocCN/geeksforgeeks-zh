# HTML 日期时间属性

> 原文:[https://www.geeksforgeeks.org/html-time-datetime-attribute/](https://www.geeksforgeeks.org/html-time-datetime-attribute/)

HTML 中的 **<时间>日期时间属性**用于定义<时间>元素的机器可读日期/时间。日期时间以 **YYYY-MM-DDThh:mm:ssTZD** 格式插入。
**语法:**

```html
<time datetime="YYYY-MM-DDThh:mm:ssTZD"> 
```

**属性值:**该属性包含单个值 **YYYY-MM-DDThh:mm:ssTZD** ，用于指定文本被删除的日期和时间。
日期时间成分解释如下:

*   **YYYY:** 设置日期时间对象的年份(如 2009)。
*   **MM:** 设置日期时间对象的月份(如 05 表示三月)。
*   **DD:** 设置日期时间对象的月份中的某一天(如 04)。
*   **T:** 是必需的分隔符。
*   **hh:** 设置 datetime 对象的小时(如 06.00pm 为 18)。
*   **mm:** 设置日期时间对象的分钟数(如 34)。
*   **ss:** 设置日期时间对象的秒数(如 40)。
*   **TZD:** 时区指示符(Z 表示祖鲁语，也称为格林威治标准时间)

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Time dateTime Attribute
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksforGeeks</h1>

    <h2>
        HTML <Time>dateTime Attribute
    </h2>

<p>Jawahar lal Nehru birthday is celebrated on 
        <time datetime="2018--11-14 12:00">
            children's day.
        </time>
    </p>

</body>

</html>
```

**输出:**

![](img/605c276efafdd2cf157e2d8e1cc22631.png)

**支持的浏览器:**T2 HTML<时间>日期时间属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队