# SVG 涡流元素类型属性

> 原文:[https://www . geeksforgeeks . org/SVG-fetubrugifelement-type-attribute/](https://www.geeksforgeeks.org/svg-feturbulenceelement-type-attribute/)

SVG`<em>`fetumble element . type 属性返回对应于*fetumble . type*元素的类型组件的 SVGAnimatedEnumeration 对象。

**语法:**

```html
var a = FETurbulenceElement.type
```

**返回值:**该属性返回对应于*feature . type*元素的类型组件的 SVGAnimatedEnumeration 对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 

    <svg width="200" height="200"
        viewBox="0 0 220 220"> 

        <filter id="FillPaint"> 

            <feTurbulence id='gfg' type="turbulence"
                baseFrequency="0.5" numOctaves="2"
                seed="5" stitchTiles="stitch" /> 

            <feDisplacementMap in2="turbulence"
                in="SourceGraphic" scale="50"
                xChannelSelector="B"
                yChannelSelector="B" /> 

        </filter> 

        <rect width="200" height="200"
            style=" fill:green; 
            filter: url(#FillPaint);" />

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.type);
            console.log("type value is :", 
                g.type.baseVal);
        </script> 
    </svg> 
</body> 

</html>
```

**输出:**

![](img/c3c5177866d1f211d402d70165d34672.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 

    <svg width="400" height="400"
        viewBox="0 0 250 250"> 

        <filter id="FillPaint"> 

            <feTurbulence id="gfg" type="fractalNoise"
                baseFrequency="2" numOctaves="2"
                seed="1" stitchTiles="stitch"
                result="turbulence" /> 

            <feDisplacementMap in2="turbulence"
                in="SourceGraphic" scale="50"
                xChannelSelector="B"
                yChannelSelector="B" /> 

        </filter> 

        <ellipse cx="100" cy="60" rx="100"
            ry="50" style=" fill: green; 
            filter: url(#FillPaint);" /> 
        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.type);
            console.log("type value is :", 
                g.type.baseVal);
        </script>
    </svg> 
</body> 

</html>
```

**输出:**

![](img/0c3e49f03b6c5d592d86d70f1991f750.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器