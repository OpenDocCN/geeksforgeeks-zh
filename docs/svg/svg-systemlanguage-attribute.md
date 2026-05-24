# SVG 系统语言属性

> 原文:[https://www.geeksforgeeks.org/svg-systemlanguage-attribute/](https://www.geeksforgeeks.org/svg-systemlanguage-attribute/)

*系统语言*属性表达了许多支持的语言标签的列表。

使用该属性的元素包括:
< a >、< altGlyph >、< animate >、< animateColor >、<animate emotion>、< animateTransform >、<音频>、<画布>、<圆圈>、<剪辑路径>、<光标>、<def <线条>、<遮罩>、<路径>、<图案>、<多边形>、<折线>、<矩形>、<设置>、< svg >、<开关>、<文字>、<文字路径>、<

***语法:***

```html
systemLanguage = "language-tags"
```

**属性值:***系统语言*属性接受上面提到的和下面描述的值

*   **语言-标签:**该属性值包括的标签有: *ar、de、nl、en-us、en-gb、en-au、en、es、fr、ja、ru 等。*

下面的例子说明了系统语言属性的使用。

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>

    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <svg viewBox="0 -20 300 350">
        <switch>
            <text systemLanguage="ar">مرحبا</text>
            <text systemLanguage="de, nl">Hallo!</text>
            <text systemLanguage="en-us">Howdy!</text>
            <text systemLanguage="en-gb">Wotcha!</text>
            <text systemLanguage="en-au">G'day!</text>
            <text systemLanguage="en">Hello!</text>
            <text systemLanguage="es">Hola!</text>
            <text>Sorry no language matched!</text>
        </switch>
    </svg>
</body>

</html>
```

**输出:**

![](img/3879cc48a129a410a9444c14d34e38a3.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>

    <h1 style="color: green; text-align: center;">
        GeeksforGeeks
    </h1>

    <svg viewBox="-30 -20 300 350">
        <switch>
            <text systemLanguage="ar">مرحبا</text>
            <text systemLanguage="de, nl">Hallo!</text>
            <text systemLanguage="es">Hola!</text>
            <text>Sorry no language matched!</text>
        </switch>
    </svg>
</body>

</html>
```

**输出:**

![](img/3ed839599a8fc1b14aba5527dfad3d35.png)