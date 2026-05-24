# SVG FEOffset.dy 属性

> 原文:[https://www.geeksforgeeks.org/svg-feoffset-dy-property/](https://www.geeksforgeeks.org/svg-feoffset-dy-property/)

**SVG FEOffset.dy 属性**返回对应于 FEOffset 元素的 *dy* 组件的 SVGAnimatedNumber 对象。

**语法:**

```html
let offset_prop = FEOffset.dy
```

**返回值:**该属性返回 FEOffset 元素 dy 成分对应的 SVGAnimatedNumber 对象。

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

                <feOffset result="offOut" 
                    dx="30" dy="30" 
                    in="SourceGraphic" id="gfg" />

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
            let feoffset = document.getElementById("gfg");
            console.log(feoffset.dy)
            console.log("dy value is : ",
                feoffset.dy.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/f42291c0aa6527303eb808372c2cc99a.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="400" height="400">
        <defs>
            <filter id="filter2" x="0" 
                y="0" width="150%" height="150%">

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
            let feoffset =
                document.getElementById("gfg");
            console.log(feoffset.dy)
            console.log("dy value is : ",
                feoffset.dy.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/98bbddb03ac33826286b852eebeb0f2d.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器