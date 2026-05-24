# SVG 宽度属性

> 原文:[https://www.geeksforgeeks.org/svg-width-attribute/](https://www.geeksforgeeks.org/svg-width-attribute/)

宽度属性定义元素的垂直长度。

**语法:**

```html
width= "width"
```

**属性值:**

*   **长度:**我们要设置宽度属性的长度。
*   **百分比:**我们要设置宽度属性的百分比。

我们将使用 width 属性来设置元素的宽度。

**示例 1:** 在本例中，我们将使用宽度属性来使用长度值设置矩形的宽度。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 900 300" 
        xmlns="http://www.w3.org/2000/svg">

        <rect y="45" x="45" width="30" 
            height="20" fill="green" />

        <rect y="90" x="45" width="30" 
            height="20" fill="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/c241d8ec4d42673c76c75e17196fa1d4.png)

**示例 2:** 在本例中，我们将使用高度属性来使用百分比值设置矩形的高度。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 900 300" 
        xmlns="http://www.w3.org/2000/svg">

        <rect y="45" x="45" width="30%" 
            height="10%" fill="green" />

        <rect y="90" x="45" width="30%" 
            height="10%" fill="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/2ed6342d2a588507e848b5e16f25d0dd.png)