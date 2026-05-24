# SVG ry 属性

> 原文:[https://www.geeksforgeeks.org/svg-ry-attribute/](https://www.geeksforgeeks.org/svg-ry-attribute/)

**ry** 属性定义 y 轴上的半径。

使用此属性的元素:

*   [<椭圆>](https://www.geeksforgeeks.org/html-svg-ellipse/)
*   [< 直肠 >](https://www.geeksforgeeks.org/html-svg-rect/)

**语法:**

```html
ry = "y-radius"
```

**属性值:**

*   **长度:**我们要设置 y 半径的长度。
*   **百分比:**我们要设置 y 半径的百分比。

我们将使用 ry 属性来设置 y 轴上的半径。

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 300 300" 
        xmlns="http://www.w3.org/2000/svg">

        <ellipse cx="50" cy="50" 
            rx="10" ry="10" fill="green" />

        <ellipse cx="100" cy="50" 
            rx="30" ry="15" fill="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/1f8bfa7f9e15398da9afd5ffcbe0d5ea.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 300 300" 
        xmlns="http://www.w3.org/2000/svg">

        <rect x="20" y="120" width="60" height="60" 
            rx="10" ry="0" fill="green" />

        <rect x="120" y="120" width="60" height="60" 
            rx="18" ry="6" fill="green" />

        <rect x="220" y="120" width="60" height="60" 
            rx="15" ry="10" fill="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/aa27e60d311a89747feb6cc71583740e.png)