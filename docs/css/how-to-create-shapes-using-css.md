# 如何使用 CSS 创建形状？

> 原文:[https://www . geeksforgeeks . org/如何使用-css 创建形状/](https://www.geeksforgeeks.org/how-to-create-shapes-using-css/)

在本文中，我们将使用 CSS 设计一些不同类型的形状。CSS 能够制作所有类型的形状。

*   **创建一个正方形:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .square {
            height: 50px;
            width: 50px;
            background-color: green;
        }
    </style>
</head>

<body>
    <div class="square"></div>
</body>

</html>
```

**输出:**

![](img/149efa2ad3c01f30728658d81c3d5f42.png)

*   **创建三角形**
    *   **向上:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .triangle {
            width: 0;
            height: 0;
            border-left: 25px solid transparent;
            border-right: 25px solid transparent;
            border-bottom: 50px solid green;
        }
    </style>
</head>

<body>
    <div class="triangle"></div>
</body>

</html>
```

**输出:**

![](img/a407c6cfc1dda2c12417bb2d259ddbac.png)

*   **向下:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .triangle {
            width: 0;
            height: 0;
            border-left: 25px solid transparent;
            border-right: 25px solid transparent;
            border-top: 50px solid green;
        }
    </style>
</head>

<body>
    <div class="triangle"></div>
</body>

</html>
```

**输出:**

![](img/7e03950a7fd31958d8a862fca0c3f0e5.png)

*   **创建圆:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .circle {
            height: 70px;
            width: 70px;
            background-color: green;
            border-radius: 50%;
        }
    </style>
</head>

<body>
    <div class="circle"></div>
</body>

</html>
```

**输出:**

![](img/e0606e3eeeac92312c3ab1e4ab2aba72.png)

*   **创建矩形:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .rectangle {
            height: 50px;
            width: 80px;
            background-color: green;
        }
    </style>
</head>

<body>
    <div class="rectangle"></div>
</body>

</html>
```

**输出:**

![](img/0a645a4a4d2db4d58a0293ee197d7327.png)

*   **创建平行四边形:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .parallelogram {
            width: 120px;
            height: 60px;
            transform: skew(24deg);
            background: green;
        }
    </style>
</head>

<body>
    <div class="parallelogram"></div>
</body>

</html>
```

*   **输出:**

![](img/2c620228e1cbeba30fb53d52662e4df0.png)

*   **创建椭圆形:**

## 超文本标记语言

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html>

<head>
    <style>
        .oval {
            height: 200px;
            width: 400px;
          border-radius: 50%;
            background-color: green;
        }
    </style>
</head>

<body>
    <div class="oval"></div>
</body>

</html>
```

*   **输出:**

![](img/c8883088cfa0187ecff503e1d88b3d5b.png)