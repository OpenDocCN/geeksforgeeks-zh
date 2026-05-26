# SVG feSpecularLighting.in1 属性

> 原文: [https://www.geeksforgeks.org/svg-fespecularlighting-in1-property/](https://www.geeksforgeks.org/svg-fespecularlighting-in1-property/)

`SVG feSpecularLighting.in1` 属性返回与 `feSpecularLighting` 元素的 `in1` 组件对应的 `SVGAnimatedString` 对象。

## 语法

```html
var a = FESpecularLighting.in1
```

## 返回值

该属性返回对应于 `feSpecularLighting` 元素的 `in1` 组件的 `SVGAnimatedString` 对象。

## 示例

### 示例 1

```html
<!DOCTYPE html>
<html>

<body>
    <svg height="200" width="200">
        <filter id="filter">
            <feSpecularLighting specularExponent="5" 
                lighting-color="gold" result="light" 
                in="SourceGraphic" id="gfg">
                <fePointLight x="100" y="100" z="100" />
            </feSpecularLighting>
            <feComposite in="SourceGraphic" 
                in2="specOut" operator="arithmetic" 
                k1="1" k2="0" k3="1" k4="0" />
        </filter>
        <rect x="1" y="1" width="200" height="200" 
            style="stroke: #000000; fill: green; 
            filter: url(#filter);" />
        <rect x="50" y="50" width="100" height="100" 
            style="stroke: #000000; fill: green; 
            filter: url(#filter);" />
        <g fill="#FFFFFF" stroke="black" 
            font-size="10" font-family="Verdana" />
        <text x="60" y="100">GeeksForGeeks</text>
        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1);
            console.log("in1 value is : ", g.in1.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/a67b97d2a100cdaff04035d49ec124e5.png)

### 示例 2

```html
<!DOCTYPE html>
<html>

<body>
    <svg height="200" width="200" 
        viewBox="0 0 220 220">
        <filter id="filter">
            <feSpecularLighting specularExponent="2" 
                lighting-color="shadow" result="light"
                in="BackgroundImage" id="gfg">
                <fePointLight x="200" y="200" z="100" />
            </feSpecularLighting>
            <feComposite in="SourceGraphic" 
                in2="specOut" operator="arithmetic" 
                k1="0" k2="1" k3="1" k4="0" />
        </filter>
        <rect x="40" y="40" width="200" height="200" 
            style="stroke: black; fill: green; 
            filter: url(#filter);" />
        <circle cx="130" cy="130" r="50" 
            style="fill: black; filter:url(#filter)" />
        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1);
            console.log("in1 value is : ", g.in1.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/fd456a18765d0d14288fa22685408ac9.png)

### 示例 3

```html
<!DOCTYPE html>
<html>

<body>
    <svg height="200" width="200" 
        viewBox="0 0 220 220">
        <filter id="filter">
            <feSpecularLighting in="BackgroundImage" 
                specularConstant="0.8" surfaceScale="1" 
                specularExponent="20" kernelUnitLength="1"
                lighting-color="red" id="gfg">
                <fePointLight x="100" y="100" z="220" />
            </feSpecularLighting>
            <feComposite in="SourceGraphic" in2="specOut" 
                operator="arithmetic" k1="0" k2="1" 
                k3="1" k4="0" />
        </filter>
        <rect x="60" y="60" width="150" height="150" 
            style="stroke: #000000; fill: lightgreen; 
                filter: url(#filter);" />
        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1);
            console.log("in1 value is : ", g.in1.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/2dad26587b1bf5830296748338dd0ea3.png)

## 支持的浏览器

*   `Google Chrome`
*   `Edge`
*   `Firefox`
*   `Safari`
*   `Opera`
*   `Internet Explorer`