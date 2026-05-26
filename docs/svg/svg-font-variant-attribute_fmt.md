# SVG 字体变体属性

> 原文:[https://www.geeksforgeeks.org/svg-font-variant-attribute/](https://www.geeksforgeeks.org/svg-font-variant-attribute/)

**字体变体** 属性指示文本或字体将在中呈现的变体。

**语法:**

```html
`font-variant = "variant"`
```

**属性值:**

*   **默认值:** `正常值`为默认值。
*   **可动画值:** `可动画值`为可动画值。
*   **其他值:** `小写值`是其他值的一个例子。

我们将使用 `font-variant` 属性来设置字体的变体。

### 示例1

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 250 30" 
        xmlns="http://www.w3.org/2000/svg">

        <text y="20" font-variant="Normal">
            GeeksforGeeks
        </text>
    </svg>
</body>

</html>
```

**输出:**

![](img/6437f5192776c4d4bfc0dd1ea6056f50.png)

### 示例2

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 250 30" 
        xmlns="http://www.w3.org/2000/svg">

        <text x="10" y="20" font-variant="small-caps">
            GeeksforGeeks
        </text>
    </svg>
</body>

</html>
```

**输出:**

![](img/5aa46541645cc175419d54ba9b97f418.png)