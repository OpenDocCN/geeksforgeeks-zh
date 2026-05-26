# SVG 长度调整属性

> 原文：[https://www.geeksforgeeks.org/svg-lengthadjust-attribute/](https://www.geeksforgeeks.org/svg-lengthadjust-attribute/)

`lengthAdjust`属性用于决定文本在`textLength`属性定义的长度内的拉伸。使用该属性的元素有`<text>`、`<textPath>`、`<tref>`和`<tspan>`。

**语法：**

```html
lengthAdjust = spacing | spacingAndGlyphs
```

**属性值：**`lengthAdjust`属性接受上面提到的和下面描述的值。

*   `spacing`：它会调整字形之间的间距，但不会拉伸或挤压字形本身。
*   `spacingAndGlyphs`：它将调整字形之间的间距和字形大小。

**注意：**`lengthAdjust`属性的默认值为`spacing`。

下面的例子说明了`lengthAdjust`属性的使用。

### 示例 1

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            font-style: italic;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1 style="color: green; 
            margin-left: 35px;
            font-size: 25px;">
        GeeksforGeeks
    </h1>

    <svg xmlns="http://www.w3.org/2000/svg">
        <g>
            <text class="geek" x="0" y="15">
                Stretched with spacing only:-
            </text>

            <text x="0" y="35" textLength="300" 
                lengthAdjust="spacing">
                A Computer Science
                portal for geeks.
            </text>
        </g>
    </svg>
</body>

</html>
```

**输出：**

![](img/436641eeac87fbc713e26f4c36692848.png)

### 示例 2

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            font-style: italic;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1 style="color: green; 
            margin-left: 35px;
            font-size: 25px;">
        GeeksforGeeks
    </h1>

    <svg xmlns="http://www.w3.org/2000/svg">
        <g>
            <text class="geek" x="0" y="15">
                Stretched with spacing
                and glyphs:-
            </text>

            <text x="0" y="35" textLength="300"
                lengthAdjust="spacingAndGlyphs">
                A Computer Science
                portal for geeks.
            </text>
        </g>
    </svg>
</body>

</html>
```

**输出：**

![](img/e680b5800dfcf9f131e25d2c39d9aa42.png)

### 示例 3

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            font-style: italic;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1 style="color: green; 
            margin-left: 35px;
            font-size: 25px;">
        GeeksforGeeks
    </h1>

    <svg xmlns="http://www.w3.org/2000/svg">
        <g>
            <text class="geek" x="0" y="15">
                Shrunk with spacing only:-
            </text>

            <text x="0" y="35" textLength="100"
                lengthAdjust="spacing">
                A Computer Science
                portal for geeks.
            </text>
        </g>
    </svg>
</body>

</html>
```

**输出：**

![](img/f08b8a1210a530a5905ec5c135aa90ac.png)

### 示例 4

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            font-style: italic;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1 style="color: green; 
            margin-left: 35px;
            font-size: 25px;">
        GeeksforGeeks
    </h1>

    <svg xmlns="http://www.w3.org/2000/svg">
        <g>
            <text class="geek" x="0" y="15">
                Shrunk with spacing
                and glyphs:-
            </text>
            <text x="0" y="35" textLength="100"
                lengthAdjust="spacingAndGlyphs">
                A Computer Science
                portal for geeks.
            </text>
        </g>
    </svg>
</body>

</html>
```

**输出：**

![](img/40e3fcedc3e4c609d9ff8f40316208ee.png)