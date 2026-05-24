# SVG `<feMerge>`标签

> 哎哎哎:# t0]https://www . geeksforgeeks . org/SVG-femerge 标签/

**<融合>** SVG 元素允许同时应用滤镜效果，而不是依次应用。< feMerge >的规范实现是将整个效果渲染到一个 RGBA 图层中，然后在输出设备上渲染结果图层。

**语法:**

```html
<feMerge> ---- </feMerge>

```

**属性:**不包含任何属性。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200">
        <filter id="feOffset" x="-40" y="-20" 
            width="100" height="200">
            <feOffset in="SourceGraphic" dx="60" dy="60" />
            <feGaussianBlur stdDeviation="5" result="blur2" />

            <feMerge>
                <feMergeNode in="offsetBlur" />
                <feMergeNode in="litPaint" />
            </feMerge>

        </filter>

        <rect x="1" y="1" width="198" height="118" 
                fill="green" stroke="blue" />
        <circle cx="100" cy="60" r="55" stroke="black" 
                stroke-width="3" fill="white" />
        <g fill="#FFFFFF" stroke="Green" font-size="10"
                font-family="Verdana">
            <text x="60" y="62">GeeksForGeeks</text>
    </svg>
</body>

</html>
```

**输出:**

![](img/7ea84666635ce192476174addc2d29f3.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200">
        <filter id="feOffset" x="-40" y="-20" 
            width="100" height="200">
            <feOffset in="blur" dx="4" dy="4" 
                result="offsetBlur" />
            <feGaussianBlur in="SourceGraphic" 
                stdDeviation="5" result="blur2" />

            <feMerge>
                <feMergeNode in="offsetBlur" />
                <feMergeNode in="litPaint" />
            </feMerge>

        </filter>

        <rect x="40" y="40" width="100" height="100"
            style="stroke: #000000; fill: lightgreen; 
            filter: url(#feOffset);" />
        <rect x="40" y="40" width="100" height="100" 
            style="stroke: #000000; fill: green;" />
        <g fill="#FFFFFF" stroke="black" font-size="10" 
            font-family="Verdana">
            <text x="50" y="90">GeeksForGeeks</text>
    </svg>
</body>

</html>
```

**输出:**

![](img/a00d7e4962077ee69ef5f93aab2b4476.png)