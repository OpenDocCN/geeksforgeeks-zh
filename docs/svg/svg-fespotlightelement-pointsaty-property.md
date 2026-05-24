# SVG fespot lightelement . points ty 属性

> 原文:[https://www . geeksforgeeks . org/SVG-fespot lightelement-point saty-property/](https://www.geeksforgeeks.org/svg-fespotlightelement-pointsaty-property/)

**SVG FESpotLightElement.pointsAtY 属性**返回与 fespot lightelement . pointsAtY 元素的 point saty 属性对应的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FESpotLightElement.pointsAtY
```

**返回值:**该属性返回对应于 fespot lightelement . pointsAtY 元素的 points saty 属性的 SVGAnimatedNumber 对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 
    <div style="color: green;"> 
        <h1> 
            GeeksforGeeks 
        </h1> 

        <svg viewBox="0 0 1120 350"
            xmlns="http://www.w3.org/2000/svg"> 

            <filter id="Geek" width="100%"
                height="100%"> 
                <feDiffuseLighting in="SourceGraphic"> 
                    <feSpotLight x="120" y="120"
                        z="50" pointsAtZ="5" pointsAtX="5" 
                        pointsAtY="5" id="Geek2"/> 
                </feDiffuseLighting> 
            </filter> 

            <rect width="300" height="300"
                style="filter: url(#Geek);"/>

                <text x="50" y="60">GeeksForGeeks</text>
            <script type="text/javascript">
                var g = document.getElementById("Geek2");
                console.log(g.pointsAtY);
                console.log("pointAtY value of feSpotLight "+
                "element is : "+g.pointsAtY.baseVal)
            </script>
        </svg> 
    </div> 
</body> 

</html>
```

**输出:**

![](img/62d15d36685d3ec17fc2cf1c788f628a.png)

**例 2:**

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
                    lighting-color="#FFF"> 

                    <feSpotLight x="400" y="400"
                        z="900" pointsAtZ="5" pointsAtX="5" 
                        pointsAtY="5" limitingConeAngle="9"
                        specularExponent="10" id="gfg"/> 
                </feSpecularLighting> 

                <feComposite in="SourceGraphic"
                    in2="spotlight" operator="out"
                    k1="0" k2="1" k3="1" k4="0" /> 
            </filter> 
        </defs> 

        <rect x="40" y="40" width="150" height="100"
            style="stroke: #000000; 
                fill: green; 
                filter: url(#spotlight);" /> 

        <g fill="#FFFFFF" stroke="black" font-size="10"
            font-family="Verdana"/> 

            <text x="50" y="90">GeeksForGeeks</text> 

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.pointsAtY);
            console.log("pointsAtY value of feSpotLight "+
            "element is : "+g.pointsAtY.baseVal)
        </script>
    </svg> 
</body> 

</html>
```

**输出:**

![](img/4ae2caed8fa30077e87573a1dff3573d.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器