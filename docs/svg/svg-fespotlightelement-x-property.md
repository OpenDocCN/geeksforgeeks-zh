# SVG FESpotLightElement.x 属性

> 原文:[https://www . geeksforgeeks . org/SVG-fespot lightelement-x-property/](https://www.geeksforgeeks.org/svg-fespotlightelement-x-property/)

**SVG***FespotLightElement . x*属性返回与 *FESpotLightElement.x* 元素的 x 属性对应的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FESpotLightElement.x

```

**返回值:**该属性返回 FESpotLightElement.x 元素的 x 属性对应的 SVGAnimatedNumber 对象。

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

        <rect x="40" y="40" width="100" 
            height="100" style="stroke: #000000; 
                fill: green; 
                filter: url(#spotlight);" />

        <g fill="#FFFFFF" stroke="black" 
            font-size="10" font-family="Verdana" />

        <text x="50" y="90">GeeksForGeeks</text>

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.x);

            console.log("x value of feSpotLight "
                + "element is : " + g.x.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/9c7186e424cc83003025585c17b6d0b0.png)

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
            console.log(g.x);
            console.log("x value of feSpotLight "
                + "element is : " + g.x.animVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/d75febdff18f9c534bcc50d33db62e3c.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧