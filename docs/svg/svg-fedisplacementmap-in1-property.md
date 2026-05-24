# SVGFe 置换图 1 属性

> 原文:[https://www . geesforgeks . org/SVG-fe 置换 mentmap-in1-property/](https://www.geeksforgeeks.org/svg-fedisplacementmap-in1-property/)

SVG`<em>`fe 置换映射. in1 属性返回对应于*fe 置换映射. in1* 元素的组件中*的 SVGAnimatedString 对象。*

**语法:**

```html
var a = FEDisplacementMap.in1
```

**返回值:**该属性返回与*元素的*组件中的*对应的**svorganimatedstring**对象。*

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg width="200" height="200"
        viewBox="0 0 220 220"> 

        <filter id="displacementFilter"> 

            <feTurbulence type="turbulence"
                baseFrequency="1"
                numOctaves="2"
                result="turbulence"/> 

            <feDisplacementMap in2="turbulence"
                in="SourceGraphic" scale="50"
                xChannelSelector="R"
                yChannelSelector="B"  id="gfg"/> 
        </filter> 

        <circle cx="100" cy="100" r="100"
            stroke="green" style= 
            "filter: url(#displacementFilter)" /> 

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1)
            console.log("in1 value is : ",
                g.in1.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/cb0ccd33e239c7fab821cb338fb60854.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 
    <svg width="200" height="200"
        viewBox="0 0 220 220"> 

        <filter id="displacementFilter"> 

            <feTurbulence type="turbulence"
                baseFrequency="5" numOctaves="2"
                result="turbulence" /> 

            <feDisplacementMap in2="abc"
                in="SourceGraphic" scale="200"
                xChannelSelector="B"
                yChannelSelector="R" id="gfg" /> 
        </filter> 

        <rect width="250" height="250" style
        ="filter: url(#displacementFilter)" /> 

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.in1)
            console.log("in1 value is : ",
                g.in1.baseVal)
        </script>
    </svg> 
</body> 

</html> 
```

**输出:**

![](img/75fbbb3e91e51fc0e3f8bbff61668eab.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器