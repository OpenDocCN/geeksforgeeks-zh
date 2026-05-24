# SVG 路径长度属性

> 原文:[https://www.geeksforgeeks.org/svg-pathlength-attribute/](https://www.geeksforgeeks.org/svg-pathlength-attribute/)

*路径长度*属性以用户单位定义路径的总长度。使用该属性的元素有: *<圆>、<椭圆>、<线>、<路径>、<多边形>、<折线>、*和 *<矩形>T5】*

**语法:**

```html
pathLength = number
```

**属性值:***路径长度*属性接受上面提到的和下面描述的值

*   **数:**可以是带小数的数，也可以是整数。

下面的例子说明了*路径长度*属性的使用。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        path {
            stroke: green;
            stroke-width: 5;
            stroke-dasharray: 12;
        }
    </style>
</head>

<body>
    <h2 style="color: green;">
        GeeksforGeeks
    </h2>

    <svg viewBox=" 0 0 400 60"
        xmlns="http://www.w3.org/2000/svg">

        <path d="M 0,10 h100" />

        <path d="M 0,20 h100" pathLength="80" />
    </svg>
</body>

</html>
```

**输出:**

![](img/80d3ea3b24c9e62147e202e5dc63a44f.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        path {
            stroke: green;
            stroke-width: 5;
            stroke-dasharray: 12;
        }
    </style>
</head>

<body>
    <h2 style="color: green;">
        GeeksforGeeks
    </h2>
    <svg viewBox="0 20 400 60"
        xmlns="http://www.w3.org/2000/svg">
        <path d="M 0,30 h100" pathLength="60" />
        <path d="M 0,40 h100" pathLength="30" />
        <path d="M 0,50 h100" pathLength="10" />
    </svg>
</body>

</html>
```

**输出:**

![](img/cfa0e2643007794ea4b724a70b3051e1.png)