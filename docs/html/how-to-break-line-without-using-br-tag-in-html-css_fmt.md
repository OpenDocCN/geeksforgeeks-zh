# 如何在 HTML / CSS 中不使用 `<br>` 标签的情况下断线？

> 原文：[https://www.geeksforgeeks.org/how-to-break-line-without-using-br-tag-in-html-css/](https://www.geeksforgeeks.org/how-to-break-line-without-using-br-tag-in-html-css/)

不使用 `<br>` 标记，使用块级元素断线。不用 `<br>` 标签断线的方法有很多。使用的属性如下：

*   `white-space: pre` 用于使元素行为类似于 `<pre>` 标签。
*   `display: block;` 将元素的显示属性设置为块。

**例 1：** 本例使用 `white-space` 来预断线。

```html
<!DOCTYPE html> 
<html>

<head> 
    <title> 
        Line break withoutusing br tag
    </title> 
</head>

<body style = "text-align:center;">

<h1 style = "color:green;" > 
        GeeksForGeeks 
    </h1>

<div style="white-space: pre">
        GeeksforGeeks
        GeeksforGeeks
    </div>
</body>

</html>                     
```

**输出：**
![](img/97d915de7bc2e1baf5467b86f4c3ea42.png)

**例 2：** 本例使用 `display` 属性断线。

```html
<!DOCTYPE html> 
<html>

<head> 
    <title> 
        Line break using display property
    </title>

<style>
        p span {
            display: block;
        }
    </style>
</head>

<body style = "text-align:center;">

<h1 style = "color:green;" > 
        GeeksForGeeks 
    </h1>

<p>
        <span>GeeksforGeeks_1</span>
        <span>GeeksforGeeks_2</span>
    </p>
</body>

</html>                     
```

**输出：**
![](img/f7b7a4406ba388b852ca3816ee8f1323.png)