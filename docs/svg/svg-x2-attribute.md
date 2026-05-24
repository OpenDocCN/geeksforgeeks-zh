# SVG x2 属性

> 原文:[https://www.geeksforgeeks.org/svg-x2-attribute/](https://www.geeksforgeeks.org/svg-x2-attribute/)

**x2** 属性用于指定绘制需要多个坐标的 SVG 元素的第一个 x 坐标。

使用此属性的元素:

*   [<线>](https://www.geeksforgeeks.org/html-svg-line/)
*   <线性梯度>

**语法:**

```html
x2 = "x2-coordinate"
```

**属性值:**

*   **长度:**我们要设置 x2 坐标的长度。
*   **百分比:**我们要设置 x2 坐标的百分比。

我们将使用 x2 属性来设置 x2 坐标。

**示例 1:** 在本例中，我们将使用长度值。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 70 70" 
        xmlns="http://www.w3.org/2000/svg">

        <line x1="7" x2="3" y1="1" 
            y2="9" stroke="red" />

        <line x1="7" x2="7" y1="1" 
            y2="9" stroke="green" />

        <line x1="7" x2="11" y1="1" 
            y2="9" stroke="blue" />
    </svg>
</body>

</html>
```

**输出:**

![](img/532f04d3f4bd3323d83efc016002242d.png)

**示例 2:** 在本例中，我们将使用百分比值。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 70 70" 
        xmlns="http://www.w3.org/2000/svg">

        <line x1="21%" x2="9%" y1="1" 
                y2="9" stroke="red" />

        <line x1="21%" x2="21%" y1="1" 
                y2="9" stroke="green" />

        <line x1="21%" x2="33%" y1="1" 
                y2="9" stroke="blue" />
    </svg>
</body>

</html>
```

**输出:**

![](img/6eeeb3225a52c8fb492f6e057eeb7550.png)