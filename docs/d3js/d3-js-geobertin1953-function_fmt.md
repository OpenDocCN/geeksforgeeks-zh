# D3.js geoBertin1953() 函数

> 原文: [https://www.geeksforgeeks.org/d3-js-geobertin1953-function/](https://www.geeksforgeeks.org/d3-js-geobertin1953-function/)

D3.js 中的 `geoBertin1953()` 函数用于绘制雅克·贝尔坦 1953 年的投影。它根据给定的 GeoJSON 数据制作了贝克·伯廷 1953 年的投影图。

## 语法

`d3.geoBertin1953()`

## 参数

此方法不接受任何参数。

## 返回值

该方法返回 Bertin1953 投影。

## 示例

下面的例子做了柏丁 1953 年对非洲的投影。

### HTML

```html
<!DOCTYPE html> 
<html lang="en">

<head> 
    <meta charset="UTF-8" /> 
    <meta name="viewport"
        content="width=device-width, 
                initial-scale=1.0"/>
    <script src=
        "https://d3js.org/d3.v4.js">
    </script>
    <script src=
        "https://d3js.org/d3-geo-projection.v2.min.js">
    </script>
</head>

<body> 
    <div style="width:400px; height:300px;"> 
        <svg width="600" height="300"> 
        </svg> 
    </div>

<script>
        var svg = d3.select("svg"),
            width = +svg.attr("width"),
            height = +svg.attr("height");

        // Bertin1953 projection
        var gfg = d3.geoBertin1953()
            .scale(width / 1.5 / Math.PI)
            .translate([width / 2, height / 2])

        // Loading the json data 
        d3.json("https://raw.githubusercontent.com/"
            + "janasayantan/datageojson/master/"
            + "geoAfrica.json", 
            function(data){
                // Draw the map
                svg.append("g")
                    .selectAll("path")
                    .data(data.features)
                    .enter().append("path")
                    .attr("fill", "black")
                    .attr("d", d3.geoPath()
                        .projection(gfg)
                    )
                    .style("stroke", "#ffff")
        })
    </script>
</body>

</html>
```

## 输出

![](img/e32905d20bee0cd81e61c016228f42a9.png)

贝尔蒂恩 1953 年投影