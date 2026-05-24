# SVG FEDropShadow.in1 属性

> 原文:[https://www . geesforgeks . org/SVG-Fe drop shadow-in1-property/](https://www.geeksforgeeks.org/svg-fedropshadow-in1-property/)

**SVG FEDropShadow.in1 属性**返回对应于 Fe 置换映射. in1 元素的 in1 组件的 SVGAnimatedstring 对象。

**语法:**

```html
var a = FEDropShadow.in1
```

**返回值:**这个属性返回对应于 fe 置换映射 1 元素的 in1 成分的 SVGAnimatedstring 对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg width="200" height="200"> 
        <defs> 
            <filter id="drop_shadow"
                filterUnits="objectBoundingBox"
                x="-50%" y="-60%" width="250%"
                height="250%"> 

                <feDropShadow in="SourceGraphic"
                    dx="1" dy="1" stdDeviation="30"
                    flood-color="darkgreen" id="gfg"/> 
            </filter> 
        </defs> 

        <rect x="40" y="40" width="100" height="100"
            style="stroke: #000000; 
                fill: lightgreen; 
                filter: url(#drop_shadow);" /> 

        <g fill="#FFFFFF" stroke="black"
            font-size="10" font-family="Verdana"> 
            <text x="50" y="90">GeeksForGeeks</text> 
        </g>
        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1)
            console.log("in1 value is : ",g.in1.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/a64d44c5c182a01a9027b8c8e17e6ddc.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg width="200" height="200"> 
        <defs> 
            <filter id="blur"
                filterUnits="objectBoundingBox"
                x="-10%" y="-10%" width="300%"
                height="300%"> 

                <feDropShadow in="StrokePaint"
                    dx="1" dy="1" stdDeviation="30"
                    flood-color="darkgreen" id="gfg"/> 
            </filter> 
        </defs>

        <circle cx="100" cy="60" r="55"
            stroke="darkgreen" stroke-width="3"
            fill="Lightgreen"
            style="stroke: filter: url(#blur);" /> 

        <g fill="#FFFFFF" stroke="Green"
            font-size="10" c font-family="Verdana"/> 
            <text x="60" y="62">GeeksForGeeks</text> 

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1)
            console.log("in1 value is : ",g.in1.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/5bdcff81dde6ac8b4568b1a1aefb5bd5.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧