# 如何在一个声明中设置不同的背景属性？

> 原文: [https://www.geeksforgeeks.org/how-to-set-different-background-properties-in-one-declaration/](https://www.geeksforgeeks.org/how-to-set-different-background-properties-in-one-declaration/)

我们将在本文中使用速记属性来设置不同的背景属性。

*   为了减少 CSS 代码的长度，我们可以通过`速记属性`在一行中声明背景属性。
*   通过这个属性，我们可以在一行中定义不同的背景属性，而不是在多行中使用`background-color`、`background-image`和其他属性。

`速记属性`允许您用单个属性指定一组相关的 CSS 属性。它们将相关的属性组合成一种速记形式。在大多数情况下，如果您省略了一个可选值，浏览器会设置一个默认值。

**语法:**

> `background: bg-color bg-image-position/bg-size bg-repeat bg-origin bg-clip bg-attachment initial|inherit;`

## 例 1

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            background: skyblue url("image.png") no-repeat center;
            margin-right: 200px;
        }
    </style>
</head>

<body>
    <h1>Shorthand Property</h1>

    <p>You can see that background property are given in a single declaration</p>

</body>

</html>
```

**输出:**

![输出截图](img/a681ba3e030e2b7c3a50c00c07ee2530.png)

## 示例 2: 具有多个图像的速记属性

```html
<!DOCTYPE html>
<html>

<head>
    <title>Shortand property</title>
    <style>
        body {
            background: url(image.png) left no-repeat,
            url(image2.png) right bottom no-repeat #ffffff;
        }
    </style>
</head>

<body>
    <center>
        <h1>Shorthand Property</h1>
        <p>The background property is a shorthand property for specifying all the background properties in one declaration.</p>
        <p>Here, we took the example of adding multiple background images and aligned text between them </p>
        <p>As we have used multiple background images, the background-color parameter is moved to the end of the list</p>

    </center>
</body>

</html>
```

**输出:**

![输出截图](img/14a3baa886e480bd941636f2beeefcde.png)