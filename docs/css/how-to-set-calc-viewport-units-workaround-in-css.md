# 如何在 CSS 中设置计算视口单位变通方法？

> 原文:[https://www . geesforgeks . org/how-set-calc-viewport-units-working-in-CSS/](https://www.geeksforgeeks.org/how-to-set-calc-viewport-units-workaround-in-css/)

在 HTML 网页中，当对 CSS 属性应用值时，通过使用 **calc()** 函数来执行计算。

**语法:**

```html
element {

    // CSS property
    property : calc( expression) 
}

```

**属性:****计算()**函数以单个表达式的形式获取参数。该值成为表达式的结果。甚至表达式是遵循标准优先规则的许多运算符的组合。

*   +加法
*   –减法
*   *乘法。任何参数都应该是一个数字
*   /部门。右边应该是一个数字

编写语法时必须小心，并且必须注意以下几点。

1.  **+** 和**–**运算符必须用空格包围，即高度(100%-30px)被认为是无效的，但高度(100%-30px)是有效的表达式。对于 **/** 和 ***** 操作员来说，白色间距不是必需的，但强烈推荐。
2.  除以 0 会导致错误。

**例 1:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <title>
        CSS Calc Viewport Units Workaround
    </title>

    <style>
        body {
            background-color: rgb(30, 240, 30);
        }

        h1 {
            color: rgb(30, 240, 30);
        }

        div {
            width: calc(100% - 100px);

            /* Using the calc() func to change the 
               width of the div element by 100px */
            border: 1px solid black;
            background-color: white;
            margin-top: 50px;
            text-align: center;
        }
    </style>
</head>

<body>
    <div>
        <h1>working of the calc() function</h1>
    </div>
</body>

</html>
```

**输出:**
![](img/f51cdf8e4ca759f6883b1a0adcb05cb3.png)

**例 2:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <title>
        CSS Calc Viewport Units Workaround
    </title>

    <style>
        body {
            background-color: rgb(30, 240, 30);
        }

        h1 {
            color: rgb(30, 240, 30);

            /* Using the calc() func to change 
            the font size of the h1 element */
            font-size: calc(1.5rem + 3vw);
        }

        div {
            width: calc(100% - 100px);
            border: 1px solid black;
            background-color: white;
            margin-top: 50px;
            text-align: center;
        }
    </style>
</head>

<body>
    <div>
        <h1> working of the calc() function</h1>
    </div>
</body>

</html>
```

**输出:**
![](img/63fb5e318edebb720925a030c430e138.png)