# SVG 元素类名属性

> 原文:[https://www . geesforgeks . org/SVG-element-class name-property/](https://www.geeksforgeeks.org/svg-element-classname-property/)

**SVG 元素.类名属性**用于返回给定元素的类名。

**语法:**

```html
var cName = element.className

```

**返回值:**该属性返回元素的类名。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="350" height="350" 
        xmlns="http://www.w3.org/2000/svg">

        <a href="https://www.geeksforgeeks.org" 
            id="gfg" class="Geeks">

            <text x='100' y='100' 
                font-size="50px">GfG
            </text>
        </a>

        <script>
            var g = document.getElementById('gfg');
            console.log(g.className)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/0bf1a0c4d8527f084a51f804c613a20e.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="350" height="350" 
        xmlns="http://www.w3.org/2000/svg">

        <a href="https://www.geeksforgeeks.org" 
            id="gfg" class="geeks">

            <circle cx='100' cy='100' r="80"></circle>
        </a>
        <script>
            var g = document.getElementById('gfg');
            console.log(g.className)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/cdf570f40464dd42b136557e994d8f2d.png)