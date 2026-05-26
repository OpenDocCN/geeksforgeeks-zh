# SVG `text-anchor` 属性

> 原文: [https://www.geeksforgeeks.org/svg-text-anchor-attribute/](https://www.geeksforgeeks.org/svg-text-anchor-attribute/)

`text-anchor` 属性用于对齐自动换行或预格式化的文本。包裹区域由相对于给定点的 `inline-size` 属性决定。在多行文本的情况下，对每行进行对齐。仅对以下元素有影响：`<altGlyph>`、`<text>`、`<textPath>`、`<tref>`、`<tspan>`。

### 语法

```html
text-anchor = start | middle | end
```

### 属性值

`text-anchor` 属性接受上面提到的和下面描述的值：

*   `start`: 使用该属性值，字符对齐，使得文本字符串的开始位于初始的当前文本位置。
*   `middle`: 使用该属性值，字符对齐，使得文本字符串的中间位于当前文本位置。
*   `end`: 使用该属性值，字符被移动，使得最终渲染文本的结束位于初始的当前文本位置。

### 示例 1

以下示例说明了 `text-anchor` 属性的使用。

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        text {
            font: 20px sans-serif;
        }
    </style>
</head>
<body>
    <svg viewBox="0 0 420 420" xmlns="http://www.w3.org/2000/svg">
        <path d="M60 15 L60, 50 M30, 40 L90, 40" stroke="green" />
        <text text-anchor="start" x="60" y="40" stroke="green">
            GeeksforGeeks
        </text>
        <circle cx="60" cy="40" r="3" fill="green" />
    </svg>
</body>
</html>
```

**输出:**

![](img/3287c3bd62d7c3570c6fedae6e8babff.png)

### 示例 2

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        text {
            font: 20px sans-serif;
        }
    </style>
</head>
<body>
    <svg viewBox="0 0 420 420" xmlns="http://www.w3.org/2000/svg">
        <path d="M60 15 L60, 50 M30, 40 L90, 40" stroke="green" />
        <text text-anchor="middle" x="60" y="40" stroke="green">
            GeeksforGeeks
        </text>
        <circle cx="60" cy="40" r="3" fill="green" />
    </svg>
</body>
</html>
```

**输出:**

![](img/434e975b8b5ec49ffbd96bbcbc985a16.png)

### 示例 3

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        text {
            font: 20px sans-serif;
        }
    </style>
</head>
<body>
    <svg viewBox="0 0 420 420" xmlns="http://www.w3.org/2000/svg">
        <path d="M60 15 L60, 50 M30, 40 L90, 40" stroke="green" />
        <text text-anchor="end" x="60" y="40" stroke="green">
            GeeksforGeeks
        </text>
        <circle cx="60" cy="40" r="3" fill="green" />
    </svg>
</body>
</html>
```

**输出:**

![](img/f34becd0705a8d36b8758f300d7be1fc.png)