# SVG 到属性

> 原文:[https://www.geeksforgeeks.org/svg-to-attribute/](https://www.geeksforgeeks.org/svg-to-attribute/)

SVG`<strong>`to 属性表示属性的初始值。与属性中的**搭配使用。**

**语法:**

```html
to = "number"

```

**属性值:**

*   **数字:**这个属性值保存了我们想要设置属性的数字。

我们将使用 to 属性来设置初始值。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <rect x="10" y="10">
            <animate attributeName="width" 
                fill="freeze" from="100" 
                to="150" dur="3s" />

            <animate attributeName="height" 
                fill="freeze" from="100" 
                to="150" dur="3s" />
        </rect>
    </svg>
</body>

</html>
```

**输出:**

![](img/6c0448a4b537fa9255d3e0e1d4d4d385.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <rect x="10" y="10" fill="green">
            <animate attributeName="width" 
                fill="freeze" from="100" 
                to="150" dur="3s" />

            <animate attributeName="height" 
                fill="freeze" from="100" 
                to="150" dur="3s" />
        </rect>
    </svg>
</body>

</html>
```

**输出:**

![](img/236eab9a04557db648173c97a7735338.png)