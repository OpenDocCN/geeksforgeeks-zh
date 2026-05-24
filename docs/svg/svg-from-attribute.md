# 属性

中的 SVG

> 原文:[https://www.geeksforgeeks.org/svg-from-attribute/](https://www.geeksforgeeks.org/svg-from-attribute/)

来自属性的**表示一个属性的初始值，与**到**属性**一起使用。

**语法:**

```html
from="number"

```

**属性值:**

*   **编号:**我们要从属性设置的编号

我们将使用 from 属性来设置初始值。

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