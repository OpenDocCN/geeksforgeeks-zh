# SVG y2 属性

> 原文:[https://www.geeksforgeeks.org/svg-y2-attribute/](https://www.geeksforgeeks.org/svg-y2-attribute/)

**y2** 属性用于指定绘制需要多个坐标的 SVG 元素的第一个 y 坐标。

使用此属性的元素:

*   [<线>](https://www.geeksforgeeks.org/html-svg-line/)
*   <线性梯度>

**语法:**

```html
y2 = "y2-coordinate"
```

**属性值:**

*   **长度:**我们要设置 y2 坐标的长度。
*   **百分比:**我们要设置 y2 坐标的百分比。

我们将使用 y2 属性来设置 y2 坐标。

**示例 1:** 在本例中，我们将使用长度值。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 70 70" 
        xmlns="http://www.w3.org/2000/svg">

        <line x1="1" x2="9" y1="7" 
            y2="5" stroke="green" />

        <line x1="1" x2="9" y1="9" 
            y2="5" stroke="green" />

        <line x1="1" x2="9" y1="11" 
            y2="5" stroke="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/f9455a7a25e5608c366787334a95ddf9.png)

**示例 2:** 在本例中，我们将使用百分比值。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 70 70" 
        xmlns="http://www.w3.org/2000/svg">

        <line x1="4%" x2="36%" y1="7" 
            y2="5" stroke="green" />

        <line x1="4%" x2="36%" y1="9" 
            y2="5" stroke="green" />

        <line x1="4%" x2="36%" y1="11" 
            y2="5" stroke="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/e72da372eb057b7fcccf504a47a25b05.png)