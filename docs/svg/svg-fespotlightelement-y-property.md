# SVG FESpotLightElement.y 属性

> 原文:[https://www . geeksforgeeks . org/SVG-fespot lightelement-y-property/](https://www.geeksforgeeks.org/svg-fespotlightelement-y-property/)

**SVG***FESpotLightElement.y*属性返回与 fespot lightelement . y 元素的 y 属性对应的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FESpotLightElement.y

```

**返回值:**这个属性返回对应于 FESpotLightElement.y 元素 y 属性的 SVGAnimatedNumber 对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200">
        <defs>
            <filter id="spotlight">
                <feSpecularLighting result="spec3" 
                    in="blur3" specularConstant="1.2" 
                    specularExponent="7"
                    lighting-color="#FFF">

                    <feSpotLight x="400" y="400" 
                        z="900" limitingConeAngle="9" 
                        id="gfg" />
                </feSpecularLighting>

                <feComposite in="SourceGraphic" 
                    in2="spotlight" operator="out" 
                    k1="0" k2="1" k3="1" k4="0" />
            </filter>
        </defs>

        <rect x="40" y="40" width="100" height="100" 
            style="stroke: #000000; 
                fill: green; 
                filter: url(#spotlight);" />

        <g fill="#FFFFFF" stroke="black" 
            font-size="10" font-family="Verdana" />

        <text x="50" y="90">GeeksForGeeks</text>

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.y);

            console.log("y value of feSpotLight "
                + "element is : " + g.y.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/9d2421a5ad83c673c58a0d99dd179756.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200">
        <defs>
            <filter id="FillPaint">
                <feSpecularLighting result="spec3" 
                    in="blur3" specularConstant="1.2" 
                    specularExponent="7"
                    lighting-color="#FFF">

                    <feSpotLight x="600" y="600" 
                        z="1200" pointAtX="400" 
                        pointAtY="400" pointAtZ="400"
                        limitingConeAngle="9" id="gfg" />
                </feSpecularLighting>

                <feComposite in="SourceGraphic" 
                    in2="spotlight" operator="out" 
                    k1="0" k2="1" k3="1" k4="0" />
            </filter>
        </defs>

        <rect x="1" y="1" width="198" height="118" 
            style="stroke: #000000; fill: black; 
                  filter: url(#FillPaint);" />

        <circle cx="100" cy="60" r="55" 
            stroke="darkgreen" stroke-width="3" 
            fill="Lightgreen"
            style="stroke: filter: url(#FillPaint);" />

        <g fill="#FFFFFF" stroke="Green" 
            font-size="10" c font-family="Verdana" />

        <text x="60" y="62">GeeksForGeeks</text>

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.y);
            console.log("y value of feSpotLight "
                + "element is : " + g.y.animVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/bafd635a0b74393598123728ba74eccb.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器