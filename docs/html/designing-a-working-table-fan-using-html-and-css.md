# 使用 HTML 和 CSS 设计工作台风扇

> 原文:[https://www . geeksforgeeks . org/design-a-work-table-fan-use-html-and-CSS/](https://www.geeksforgeeks.org/designing-a-working-table-fan-using-html-and-css/)

在本文中，我们将使用 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 和 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 设计一个工作台风扇。

**使用的 HTML 标签列表:**

*   **折线:**[<折线>](https://www.geeksforgeeks.org/svg-polyline-element/) 元素用于创建 HTML < svg >元素，该元素是 svg 图形的容器，任何形状仅由直线组成
*   [**div**](https://www.geeksforgeeks.org/div-tag-html/)**:**<div>标签定义了 HTML 文档中的一个部分或一个部分。
*   [**svg**](https://www.geeksforgeeks.org/html-svg-basics/)**:**HTML<SVG>元素是 SVG 图形的容器
*   [**圆**](https://www.geeksforgeeks.org/tag/circle/)**:**HTML<圆>元素用于创建圆
*   [**样式**](https://www.geeksforgeeks.org/html-style-tag/)**:**HTML<样式>元素用于提供内部 CSS。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .blade_container {
            width: 180px;
            height: 180px;
            margin: auto;
            margin-top: 50px;
            animation: blade 1s linear infinite;
        }

        @keyframes blade {
            0% {
                transform: rotate(360deg);
            }
        }

        .rode {
            width: 15px;
            height: 150px;
            background-color: black;
            margin: auto;
            margin-top: 0px;
        }

        .main_container {
            background-color: #308D46;
            border-radius: 50%;
            height: 180px;
            width: 180px;
            margin: auto;
        }
    </style>
</head>

<body>
    <center>
        <h3 style="color:green">Its Geek Time</h3>

        <div class="main_container">
            <div class="blade_container">
                <svg width="100%" height="100%">
                    <polyline style="stroke-linejoin:miter; 
                    stroke:white; stroke-width:12; 
                    fill:white;" points=
                    "90 90, 0 90, 90 90,
                    90 0,90 90,180 90,
                    90 90,90 180,90 90,
                    27 27,90 90,
                    153 27,90 90,
                    27 153,
                    90 90,
                    153 153" />
                </svg>
            </div>
        </div>

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210921173505/bg.png"
            style="z-index:-1;">
    </center>
</body>

</html>
```

**输出:**

![](img/cf3e455d4a02fa236adc04b700dea81e.png)