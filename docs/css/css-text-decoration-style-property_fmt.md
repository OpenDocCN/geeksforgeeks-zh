# CSS 文字装饰风格属性

> 原文: [https://www.geeksforgeeks.org/css-text-decoration-style-property/](https://www.geeksforgeeks.org/css-text-decoration-style-property/)

CSS 中的文本装饰样式属性用于设置元素的文本装饰。文字装饰属性是文字装饰线条、文字装饰风格和文字装饰色彩属性的组合。

**语法:**

```html
text-decoration-style: solid|double|dotted|dashed|wavy|initial|inherit;
```

**属性值:**

*   `solid`: 绘制一条实线。它是 `text-decoration-style` 属性的默认值。

**风格:**

```html
text-decoration-style: solid;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: solid;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: solid</b>
        <p class = "GFG1">
            This line has a solid underline.
        </p>
        <p class = "GFG2">
            This line has a solid line-through.
        </p>
        <p class = "GFG3">
            This line has a solid overline.
        </p>
    </body>
</html>
```

**输出:**
![text-decoration-style-solid](img/4e4d4d409cebafa3bbe722b9b517316a.png)

*   `double`: 绘制双实线。

**风格:**

```html
text-decoration-style: double;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: double;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: double</b>
        <p class = "GFG1">
            This line has a double underline.
        </p>
        <p class = "GFG2">
            This line has a double line-through.
        </p>
        <p class = "GFG3">
            This line has a double overline.
        </p>
    </body>
</html>
```

**输出:**
![text-decoration-style-double](img/0d348cf9d658ff2c5d17bd5335b9d124.png)

*   `dotted`: 绘制点线。

**风格:**

```html
text-decoration-style: dotted;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: dotted;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: dotted</b>
        <p class = "GFG1">
            This line has a dotted underline.
        </p>
        <p class = "GFG2">
            This line has a dotted line-through.
        </p>
        <p class = "GFG3">
            This line has a dotted overline.
        </p>
    </body>
</html>
```

**输出:**
![text-decoration-style-dotted](img/207feb915f7b9d660a00fed2f2bc80c8.png)

*   `dashed`: 绘制虚线。

**风格:**

```html
text-decoration-style: dashed;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: dashed;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: dashed</b>
        <p class = "GFG1">
            This line has a dashed underline.
        </p>
        <p class = "GFG2">
            This line has a dashed line-through.
        </p>
        <p class = "GFG3">
            This line has a dashed overline.
        </p>
    </body>
</html>
```

**输出:**
![text-decoration-style-dashed](img/9db531e9ca3924a51bafda779d1819a1.png)

*   `wavy`: 绘制波浪线。

**风格:**

```html
text-decoration-style: wavy;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: wavy;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: wavy</b>
        <p class = "GFG1">
            This line has a wavy underline.
        </p>
        <p class = "GFG2">
            This line has a wavy line-through.
        </p>
        <p class = "GFG3">
            This line has a wavy overline.
        </p>
    </body>
</html>
```

**输出:**
![text-decoration-style-wavy](img/fbbdd8bf45a4a0fef49ac804028dd599.png)

*   `initial`: 将 `text-decoration-style` 属性设置为其默认值。

**风格:**

```html
text-decoration-style: initial;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: initial;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: initial</b>
        <p class = "GFG1">
            This line has an initial underline.
        </p>
        <p class = "GFG2">
            This line has an initial line-through.
        </p>
        <p class = "GFG3">
            This line has an initial overline.
        </p>
    </body>
</html>
```

# CSS `text-decoration-style` 属性

## 初始值

```html
<p class = "GFG1">
    This line has a default underline.
</p>
<p class = "GFG2">
    This line has a default line-through.
</p>
<p class = "GFG3">
    This line has a default overline.
</p>
</body>
</html>
```

**输出:**
![text-decoration-style-initial](img/8cee41c3d6f66cd89e08a9e456c3a98b.png)

## `inherit`

此属性从其父元素继承。

**风格:**

```css
text-decoration-style: inherit;
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS text-decoration-style property
        </title>
        <!-- CSS style -->
        <style>
            p {
                text-decoration-style: inherit;
            }
            .main {
                text-decoration-style: wavy;
            }
            .GFG1 {
                text-decoration-line: underline;
            }
            .GFG2 {
                text-decoration-line: line-through;
            }
            .GFG3 {
                text-decoration-line: overline;
            }
        </style>
    </head>
    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>
        <b>text-decoration-style: inherit</b>
        <div class = "main">
            <p class = "GFG1">
                This line has a inherited underline style.
            </p>
            <p class = "GFG2">
                This line has a inherited line-through style.
            </p>
            <p class = "GFG3">
                This line has a inherited overline style.
            </p>
        </div>
    </body>
</html>
```

**输出:**
![text-decoration-style-inherit](img/d592027edd4bfae28f87fa2ef872cdfc.png)

## 支持的浏览器

`text-decoration-style` 属性支持的浏览器如下:

*   谷歌 Chrome 57.0
*   Firefox 36.0
*   Opera 44.0