# SVG fegaussionbull . stddeviation y 属性

> 原文:[https://www . geesforgeks . org/SVG-fegaussionbulr-stddeviation y-property/](https://www.geeksforgeeks.org/svg-fegaussionblur-stddeviationy-property/)

**SVG fegaussionbull . stdDeviationY 属性**返回与 fegaussionbull . stddeviation y 元素的 stddeviation y 组件对应的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FEGaussionBlur.stdDeviationY
```

**返回值:**此属性返回对应于 FEGaussionBlur.stdDeviationY 元素的 stdDeviationY 组件的 SVGAnimatedNumber 对象

**例 1:**

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg viewBox="0 0 1000 1000"> 
        <filter id="lightMe2"> 

            <feGaussianBlur in="FillPaint"
                stdDeviation="10" edgeMode="wrap" id="gfg" /> 

            <feComposite in="SourceGraphic"
                in2="light" operator="arithmetic"
                k1="1" k2="0" k3="0" k4="0" /> 

        </filter> 
        <rect x="20" y="20" width="200"
            height="200" fill="green"
            style="filter: url(#lightMe2);" /> 

        <script type="text/javascript">
                var g = document.getElementById("gfg");
                console.log(g.stdDeviationY)
                console.log("stdDeviationY value is : "
        , g.stdDeviationY.baseVal)
        </script>

    </svg> 
</body> 

</html> 
```

**输出:**

![](img/3d95b57ab749d99b6113a8db4162d0e2.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg viewBox="0 0 1000 1000"> 
        <filter id="lightMe3" x="-50"
            y="-40" width="200" height="150"> 

            <feOffset in="BackgroundImage"
                    dx="10" dy="10" /> 

            <feGaussianBlur in="offset2"
                    stdDeviation="3" id="gfg"/> 

            <feMerge> 
                <feMergeNode in="blur" /> 
                <feMergeNode in="SourceAlpha" /> 
            </feMerge> 

        </filter> 
        <rect x="20" y="20" width="200"
            height="200" fill="green"
            style="filter: url(#lightMe3);" /> 

        <script type="text/javascript">
                var g = document.getElementById("gfg");
                console.log(g.stdDeviationY)
                console.log("stdDeviationY value is : "
             , g.stdDeviationY.baseVal)
        </script>

    </svg> 
</body> 

</html> 
```

**输出:**

![](img/ac624e907b0605d6d9b2c79833b08995.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧