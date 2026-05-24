# SVG 泛色属性

> 原文:[https://www.geeksforgeeks.org/svg-flood-color-attribute/](https://www.geeksforgeeks.org/svg-flood-color-attribute/)

**泛洪颜色**属性指示使用什么颜色来泛洪当前滤镜图元子区域。

**语法:**

```html
flood-color="color"
```

**属性值:**

*   **颜色:**我们想要泛滥的颜色。

我们将使用泛色属性来设置泛色。

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 4000 2000" 
        xmlns="http://www.w3.org/2000/svg">

        <filter id="flood1">
            <feFlood flood-color="green" />
        </filter>

        <rect x="100" y="100" width="800" 
            height="800" style=
            "filter: url(#flood1);" />
    </svg>
</body>

</html>
```

**输出:**

![](img/11edb475247a48b9ac107ce73e252fa6.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 400 100" 
        xmlns="http://www.w3.org/2000/svg">

        <circle cx="50" cy="50" r="35" 
            flood-color="black" />
    </svg>
</body>

</html>
```

**输出:**

![](img/e63342635f23e49d3a4e1bb6bb72ff0e.png)