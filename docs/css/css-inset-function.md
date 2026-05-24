# CSS |插图()功能

> 原文:[https://www.geeksforgeeks.org/css-inset-function/](https://www.geeksforgeeks.org/css-inset-function/)

**嵌入()函数**是 CSS 中的一个内置函数，与 filter 属性一起用于更改图像的嵌入。
**语法:**

```html
inset( length | percentage );
```

**参数:**该功能接受单个参数**长度**，用于保存应用于图像的对比度值。参数可以是**百分比**值或**长度**。它是强制参数。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS | inset() function
    </title>

    <style>
        div {
            float: left;
            width: 185px;
            height: 185px;
            shape-outside: inset(20%);
        }

        img {
            width: 145px;
            height: 150px;
        }

        h1,
        h4 {
            text-align: center;
        }

        h1 {
            color: green;
        }

        .clr {
            color: white;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h4>CSS | inset() function</h4>
    <div>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190807114330/GFG115.png"
             alt="Sample image">
    </div>

<p>How many times- were you frustrated while looking out for a
      good collection of programming/algorithm/interview questions?
      What did you expect and what did you get? This portal has been
      created to provide well written, well thought and well explained
      solutions for selected questions. An IIT Roorkee alumnus and
      founder of GeeksforGeeks. He loves to solve programming problems
      in most efficient ways. Apart from GeeksforGeeks, he has worked
      with DE Shaw and Co. as a software developer and JIIT Noida as
      an assistant professor.It is a good platform to learn programming.
      It is an educational website. Prepare for the Recruitment drive
      of product based companies like Microsoft, Amazon, Adobe etc with
      a free online placement preparation course.</p>

</body>

</html>
```

**输出:**

![CSS inset() function](img/232483e29bba00fb0854dd88ada336d0.png)

**支持的浏览器:**以下是 **CSS | inset()函数**支持的浏览器:

*   谷歌 Chrome
*   微软边缘
*   Mozilla Firefox
*   旅行队
*   歌剧