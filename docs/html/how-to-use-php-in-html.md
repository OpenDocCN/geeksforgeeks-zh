# 如何在 HTML 中使用 PHP？

> 原文:[https://www.geeksforgeeks.org/how-to-use-php-in-html/](https://www.geeksforgeeks.org/how-to-use-php-in-html/)

在本文中，我们将在 HTML 中使用 [PHP](https://www.geeksforgeeks.org/php-introduction/) 。有各种方法来集成 PHP 和 HTML，下面将讨论其中的一些方法。

你可以给你的网页添加 PHP 标签。你只需要用 PHP 开始标记 **<将 PHP 代码括起来？php** 和 php 结束标记**？>。**这两个标签之间包装的代码被认为是 PHP 代码，在请求的文件发送到客户端浏览器之前，会在服务器端执行。

**注意:**要在 HTML 中使用 PHP，必须使用**。php** 扩展，因为在 php 中，代码是在服务器端解释和运行的。

**语法:**

```html
<html>
  <?php echo "welcome to geeksforgeeks" ?>
</html>
```

**例 1:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>Welcome To GFG</h1>

        <h2>
            <?php 
            echo "This is PHP code inside html"
            ?>
        </h2>
    </center>
</body>

</html>
```

**输出:**

![](img/ad16419d93421a1775679ac1f50f87bc.png)

html 中的 php 代码

**例 2:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>Welcome To GFG</h1>

        <p>
<?php 
echo "Complete <strong>Portal</strong> for Geeks."
?>
        <br><br>
        <?php
        echo 'Explore, learn and grow.'
        ?>
        </p>
    </center>
</body>

</html>
```

**输出:**

![](img/35132412cfa371a79ffcdbcd7cf1d47a.png)

html 中的 php