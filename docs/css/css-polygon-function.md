# CSS |多边形()函数

> 原文:[https://www.geeksforgeeks.org/css-polygon-function/](https://www.geeksforgeeks.org/css-polygon-function/)

**多边形()函数**是 CSS 中的一个内置函数，它与 filter 属性一起用于创建图像或文本的多边形。
**语法:**

```html
polygon( percentage | length);
```

**参数:**该函数接受两个参数**百分比**或**长度**，用于保存多边形大小的值。
**返回值:**根据用户需要制作多边形形状的图像或文字。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS | polygon() function
    </title>

    <style>
        div {
            float: left;
            width: 250px;
            height: 160px;
            shape-outside: polygon(0 0, 100% 50%, 0 100%);
        }

        img {
            -webkit-clip-path: polygon(0 0, 100% 50%, 0 100%);
            clip-path: polygon(0 0, 100% 50%, 0 100%);
        }

        h1,
        h4 {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h4>CSS | polygon() function</h4>
    <div>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190808143838/logsm.png"
             alt="Longtail boat in Thailand">
    </div>

<p>How many times were you frustrated while looking out
      for a good collection of programming/algorithm/interview
      questions? What did you expect and what did you get?
      This portal has been created to provide well written,
      well thought and well explained solutions for selected
      questions. An IIT Roorkee alumnus and founder of
      GeeksforGeeks. He loves to solve programming problems
      in most efficient ways. Apart from GeeksforGeeks, he
      has worked with DE Shaw and Co. as a software developer
      and JIIT Noida as an assistant professor. It is a good
      platform to learn programming. It is an educational
      website. Prepare for the Recruitment drive of product
      based companies like Microsoft, Amazon, Adobe etc with
      a free online placement preparation course.</p>

</body>

</html>
```

**输出:**

![](img/197a97b96e56bc0ba4754845c50521c6.png)

**支持的浏览器:**以下是 *CSS |多边形()函数*支持的浏览器:

*   谷歌 Chrome
*   微软边缘
*   Mozilla Firefox
*   旅行队
*   歌剧