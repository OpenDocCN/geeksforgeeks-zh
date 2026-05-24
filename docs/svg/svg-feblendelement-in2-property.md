# SVG FEBlendElement.in2 物业

> 原文:[https://www . geeksforgeeks . org/SVG-feblendelement-in2-property/](https://www.geeksforgeeks.org/svg-feblendelement-in2-property/)

**SVG FEBlendElement.in2** 属性返回对应于 *FEBlendElement.in2* 元素的 *in2* 属性的 SVGAnimatedString 对象。

**语法:**

```html
var a = FEBlendElement.in2
```

**返回值:**该属性返回与 *FEBlendElement.in2* 元素的 *in2* 属性对应的**svorganimatedstring**对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200">
        <defs>
            <filter id="spotlight">
                <feFlood result="floodFill" 
                    x="0" y="0" width="100%" 
                    height="100%" 
                    flood-color="green"
                    flood-opacity="1" />

                <feBlend in="FillPaint" 
                    in2="floodFill" 
                    mode="multiply" 
                    id="gfg" />
            </filter>
        </defs>

        <rect x="40" y="40" width="100" 
            height="100" 
            style="stroke: #000000; 
                fill: lightgreen; 
                filter: url(#spotlight);" />

        <rect x="40" y="40" width="100" 
            height="100" 
            style="stroke: #000000; 
                fill: green;" />

        <g fill="#FFFFFF" stroke="black" 
            font-size="10" 
            font-family="Verdana">

            <text x="50" y="90">
                GeeksForGeeks
            </text>
        </g>
    </svg>

    <script type="text/javascript">
        var g = document.getElementById("gfg");
        console.log(g.in2);

        console.log("in2 attribute is :", 
            g.in2.baseVal)
    </script>
</body>

</html> 
```

**输出:**

![](img/9e16d1342fdd321298357e70607132fa.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200">
        <defs>
            <filter id="Screen">
                <feBlend mode="screen" 
                    in2="BackgroundImage" 
                    in="SourceGraphic" 
                    id="gfg" />
            </filter>
        </defs>

        <rect x="1" y="1" width="198" 
            height="118" 
            style="stroke: #000000; 
                    fill: black; 
                    filter: url(#Screen);" />

        <circle cx="100" cy="60" r="55" 
            stroke="black" stroke-width="3" 
            fill="Lightgreen" />

        <g fill="#FFFFFF" stroke="Green" 
            font-size="10" 
            c font-family="Verdana">

            <text x="60" y="62">
                GeeksForGeeks
            </text>

            <script type="text/javascript">
                var g = document.getElementById("gfg");
                console.log(g.in2);
                console.log("in2 attribute is :", 
                        g.in2.baseVal)
            </script>
        </g>
    </svg>
</body>

</html>
```

**输出:**

![](img/7c516e065e7f185839fb1ab2a59185cd.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器