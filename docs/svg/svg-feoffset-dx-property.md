# SVG FEOffset.dx 属性

> 原文:[https://www.geeksforgeeks.org/svg-feoffset-dx-property/](https://www.geeksforgeeks.org/svg-feoffset-dx-property/)

**SVG FEOffset.dx 属性**返回与 FEOffset.dx 元素的 dx 组件对应的 SVGAnimatedNumber 对象。

**语法:**

```html
var a = FEOffset.dx
```

**返回值:**该属性返回 FEOffset.dx 元素的 dx 组件对应的 SVGAnimatedNumber 对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="400" height="400">
        <defs>
            <filter id="filter2" x="0" y="0" 
                width="150%" height="150%">

                <feOffset result="offOut" dx="30" 
                    dy="30" in="SourceGraphic" id="gfg" />

                <feBlend in="SourceGraphic" 
                    in2="blurOut" mode="normal" />
            </filter>
        </defs>

        <g>
            <rect x="50" y="50" width="150" 
                height="150" stroke="black" 
                stroke-width="5" fill="gray"
                filter="url(#filter2)" />
        </g>

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.dx);
            console.log("dx value is : ", g.dx.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/5583b4514ca52993fce47b803f956993.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="400" height="400">
        <defs>
            <filter id="filter2" x="0" y="0" 
                width="150%" height="150%">

                <feOffset result="offOut" dx="30" 
                    dy="30" in="SourceGraphic" id="gfg" />

                <feGaussianBlur in1="blurOut" 
                    in="offOut" stdDeviation="10" />

                <feBlend in="SourceGraphic" 
                    in2="blurOut" mode="normal" />
            </filter>
        </defs>

        <g>
            <rect x="50" y="50" width="150" 
                height="150" fill="gray" 
                filter="url(#filter2)" />
        </g>

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.dx);
            console.log("dx value is : ", g.
                dx.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/62f7c8c9bc7d5432ff5734e90de7262c.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器