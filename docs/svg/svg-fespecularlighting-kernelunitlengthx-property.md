# SVG FeSpecularllighting . kernelunitlengthex 属性

> 原文:[https://www . geeksforgeeks . org/SVG-fespelarlighting-kernelunitlongex-property/](https://www.geeksforgeeks.org/svg-fespecularlighting-kernelunitlengthx-property/)

**SVG 推测长度属性**返回对应于 feSpecularllighting . kernelUnitLengthX 元素的 kernellunitlengthex 组件的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FESpecularLighting.kernelUnitLengthX
```

**返回值:**该属性返回对应于 fespelarlighting . kernelUnitLengthX 元素的 kernellunitlengthex 组件的 SVGAnimatedNumber 对象。

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
                console.log(g.kernelUnitLengthX)
                console.log("kernelUnitLengthX value is : ",
                    g.kernelUnitLengthX.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/485b01ee4da1908f3856f1c5c715cf80.png)

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
                kernelUnitLength="3.2" 
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
                console.log(g.kernelUnitLengthX)
                console.log("kernelUnitLengthX value is : "
                 , g.kernelUnitLengthX.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/e33a8422f860d96d1be8e59388e8c666.png)

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
                specularConstant="5" kernelUnitLength="5"
                id="gfg"> 

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
                console.log(g.kernelUnitLengthX)
                console.log("kernelUnitLengthX value is : ",
                    g.kernelUnitLengthX.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/4027e3a433cf93be63f14dbb64f64414.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器