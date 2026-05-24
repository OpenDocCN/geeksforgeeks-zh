# SVG 投机照明.投机组件属性

> 原文:[https://www . geeksforgeeks . org/SVG-镜象照明-镜象组件-属性/](https://www.geeksforgeeks.org/svg-specularlighting-specularexponent-property/)

**SVG 镜象组件属性**返回对应于镜象组件元素的镜象组件组件的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FESpecularLighting.specularExponent 
```

**返回值:**该属性返回对应于镜象照明.镜象组件元素的镜象组件组件的 SVGAnimatedNumber 对象。

**例 1:**

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
                console.log(g.specularExponent)
                console.log("specularExponent value is : ",
                    g.specularExponent.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/94a77c9cb8306316edc683726fc1f439.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg height="200" width="200"> 
        <filter id="filter"> 

            <feSpecularLighting specularExponent="5"
                lighting-color="gold" result="light"
                surfaceScale="5" in="SourceGraphic"
                specularConstant="1.3" id="gfg"> 

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

        <g fill="#FFFFFF" stroke="black" font-size="10"
            font-family="Verdana"/> 

            <text x="60" y="100">GeeksForGeeks</text>

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.specularExponent)
            console.log("specularExponent value is : ",
               g.specularExponent.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/14678dfef900a690c2b6ce6c77fc388b.png)

**例 3:**

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg height="200" width="200"
        viewBox="0 0 220 220"> 

        <filter id="filter"> 
            <feSpecularLighting specularExponent="2"
                lighting-color="shadow" result="light" 
                surfaceScale="6" in="BackgroundImage" 
                specularConstant="5" id="gfg"> 

                <fePointLight x="200" y="200" z="100" /> 
            </feSpecularLighting> 

            <feComposite in="SourceGraphic"
                in2="specOut" operator="arithmetic"
                k1="0" k2="1" k3="1" k4="0" /> 
        </filter> 

        <rect x="40" y="40" width="200" height="200"
            style="stroke: black; fill: green; 
            filter: url(#filter);" /> 

        <circle cx="130" cy="130" r="50" style= 
            "fill: black; filter:url(#filter)" /> 

        <script type="text/javascript">
                var g = document.getElementById("gfg");
                console.log(g.specularExponent)
                console.log("specularExponent value is : "
               , g.specularExponent.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/94a77c9cb8306316edc683726fc1f439.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器