# SVGFeDisplacementMap.in2 属性

> 原文: [https://www.geeksforgeeks.org/svg-fedisplacementmap-in2-property/](https://www.geeksforgeeks.org/svg-fedisplacementmap-in2-property/)

`SVGFeDisplacementMap.in2` 属性返回对应于 `feDisplacementMap` 元素的 `in2` 组件的 `SVGAnimatedString` 对象。

**语法:**

```html
let in_prop = FEDisplacementMap.in2
```

**返回值:**
该属性返回对应于 `feDisplacementMap` 元素 `in2` 成分的 `SVGAnimatedString` 对象。

## 示例 1

```html
<!DOCTYPE html>
<html>
<body>
  <svg width="200" height="200"
       viewBox="0 0 220 220">

<filter id="displacementFilter">

<feTurbulence type="turbulence"
        baseFrequency="5" 
        numOctaves="2" 
        result="turbulence" />

<feDisplacementMap in2="abc" 
        in="SourceGraphic" 
        scale="200" xChannelSelector="B"
        yChannelSelector="R" id="gfg" />
    </filter>

<rect width="250" height="250" style=
          "filter: url(#displacementFilter)" />

<script type="text/javascript">
      var g = document.getElementById("gfg");
      console.log(g.in2)
      console.log("in2 value is : ",
                  g.in2.baseVal)
    </script>
  </svg>
</body>
</html>
```

**输出:**

![](img/1aa0743e5b39519d1add638264ac4862.png)

## 示例 2

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
        result="turbulence" />

<feDisplacementMap in2="turbulence"
        in="SourceGraphic"
        scale="50" 
        xChannelSelector="R" 
        yChannelSelector="B"
        id="gfg" />
    </filter>

<circle cx="100" cy="100" r="100"
            stroke="green" style=
            "filter: url(#displacementFilter)" />

<script type="text/javascript">
      var g = document.getElementById("gfg");
      console.log(g.in2);
      console.log("in2 value is : ",
                  g.in2.baseVal)
    </script>
  </svg>
</body>
</html>
```

**输出:**

![](img/228de2b873acde19fcf9a66537f10013.png)

## 支持的浏览器

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera
*   Internet Explorer