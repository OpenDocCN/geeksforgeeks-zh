# D3.js `geoKavrayskiy7()`功能

> 原文: [https://www.geeksforgeeks.org/d3-js-geokavrayskiy7-function/](https://www.geeksforgeeks.org/d3-js-geokavrayskiy7-function/)

`d3.js`中的`geoKavrayskiy7()`函数用于从给定的geojson数据绘制Kavrayskiy VII伪圆柱投影。

## 语法

```
d3.geoKavrayskiy7()
```

## 参数

此方法不接受任何参数。

## 返回

此方法返回Kavrayskiy7投影。

## 示例1

以下示例绘制世界的Kavrayskiy7投影，中心在(0, 0)，旋转0度。

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://d3js.org/d3.v4.js">
    </script>
    <script src="https://d3js.org/d3-geo-projection.v2.min.js">
    </script>
</head>

<body>
    <div style="width:700px; height:500px;">
        <center>
            <h3 style="color:black"></h3>
        </center>
        <svg width="600" height="450">
        </svg>
    </div>

<script>
        var svg = d3.select("svg"),
            width = +svg.attr("width"),
            height = +svg.attr("height");

        // Kavrayskiy7 projection with
        // the center at (0, 0) and rotation
        // of 0 degrees
        var gfg = d3.geoKavrayskiy7()
            .scale(width / 1.5 / Math.PI)
            .rotate([0, 0])
            .center([0, 0])
            .translate([width / 2, height / 2])

        // Loading the json data
        d3.json("https://raw.githubusercontent.com/" +
            "janasayantan/datageojson/master/" +
            "world.json",
            function (data) {

                // Drawing the map
                svg.append("g")
                    .selectAll("path")
                    .data(data.features)
                    .enter().append("path")
                    .attr("fill", "SaddleBrown")
                    .attr("d", d3.geoPath()
                        .projection(gfg)
                    )
                    .style("stroke", "#ffff")
            });
    </script>
</body>

</html>
```

输出:

![](img/44bb398cb979b19b7a32f9a0cb18ad2a.png)

## 示例2

以下示例绘制了世界的Kavrayskiy7投影，中心位于(-10, 0)，相对于y轴旋转90度。

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://d3js.org/d3.v4.js">
    </script>
    <script src="https://d3js.org/d3-geo-projection.v2.min.js">
    </script>
</head>

<body>
    <div style="width:700px; height:600px;">
        <center>
            <h3 style="color:black"></h3>
        </center>
        <svg width="500" height="450">
        </svg>
    </div>

<script>
        var svg = d3.select("svg"),
            width = +svg.attr("width"),
            height = +svg.attr("height");

        // Kavrayskiy7 projection with the
        // center at (0,0) and rotation of
        // 90 degrees with respect to the y-axis
        var gfg = d3.geoKavrayskiy7()
            .scale(width / 1.8 / Math.PI)
            .rotate([90, 0])
            .center([-10, 0])
            .translate([width / 2, height / 2]);

        // Loading the json data
        d3.json("https://raw.githubusercontent.com/" +
            "janasayantan/datageojson/master/" +
            "world.json",
            function (data) {

                // Draw the map
                svg.append("g")
                    .selectAll("path")
                    .data(data.features)
                    .enter().append("path")
                    .attr("fill", "grey")
                    .attr("d", d3.geoPath()
                        .projection(gfg)
                    )
                    .style("stroke", "#ffff")
            });
    </script>
</body>

</html>
```

输出:

![](img/74d775d048632a40133a0c451c240066.png)