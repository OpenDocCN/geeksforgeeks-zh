# 如何理解纯 CSS 响应设计？

> 原文:[https://www . geeksforgeeks . org/理解什么-纯 CSS-响应设计/](https://www.geeksforgeeks.org/what-to-understand-pure-css-responsive-design/)

在本文中，我们将了解 Pure。CSS 响应设计。它是一个响应性 CSS 模块的集合，可以包含在任何网络应用程序中，以创建更快、更漂亮和响应性更强的网站。简单来说，就是一个 CSS 的框架，用来在更短的时间内搭建一个美观且响应迅速的网站。纯 CSS 是雅虎开发的 CSS 框架。它有六个模块，分别是基本模块、网格模块、表单模块、按钮模块、表格模块和菜单模块。

**纯净的特征。CSS:**

*   这是一种更快更容易的网络开发方式。
*   这是一个免费的开源工具集合。
*   它创建独立于平台的网页。
*   它很容易学习和使用。
*   它有一个内置的网页和移动设备的响应设计。

**响应性设计:**

回应意味着回应，网页设计意味着设计网站。响应式设计是一种简单地根据浏览器的宽度或屏幕大小重新排列、调整、重新定位、调整整体内容和图像大小的方法。简而言之，响应设计旨在跨所有设备访问，而不管设备屏幕的大小如何。在创建响应性网站时，应牢记的一些屏幕尺寸或设备宽度  是台式机、笔记本电脑、手机和平板电脑。响应式布局是 Pure.CSS 的内置特性。它具有内部 12 列移动优先流体网格，有助于为小型、大型和中型显示屏尺寸进行响应式设计。

纯。CSS 方便了 4 个不同的关键词， *sm，md，lg，xl* &这些关键词都附带了 Pure 网格单元类( *pure-u* )，可以根据屏幕宽度生成媒体查询。“ *pure-u* ”或“ *pure-u-** ”帮助我们将显示屏的宽度分成几个部分。例如，为了使占据显示屏的 3/4 部分，我们需要将“pure-u-3-4”类包含到该特定 div 中。所有这些类的条件和媒体查询如下:

<figure class="table">

| 

#### key

 | 类名称 | [T0】 CSS media query | 

#### Applicable

 |
| --- | --- | --- | --- |
| 没有人 | 。纯-u-* | 没有人 | 总是 |
| 钐 | .纯 u-sm-* | @媒体屏幕和(最小宽度:35.5 微米) | ≥ 568px |
| 钔 | 。纯-u-md-* | @媒体屏幕和(最小宽度:48 毫米) | ≥ 768px |
| 水准仪 | 。纯-u-lg-* | @媒体屏幕和(最小宽度:64em) | ≥ 1024px |
| 特大号 | .纯 u-xl-* | @媒体屏幕和(最小宽度:80em) | ≥ 1280px |

</figure>

为了生成默认的媒体查询，使用“em”代替“px ”,以便媒体查询相应地响应网页的缩放。

**示例:**该示例描述了使用 Pure CSS 为不同的设备宽度设计响应页面。

## 超文本标记语言

```html
<html>

<head>
    <title> pure.css </title>
    <meta name="viewport" 
          content="width=device-width, initial-scale = 1">
    <link rel="stylesheet" 
          href=
"https://unpkg.com/purecss@2.0.3/build/pure-min.css">
    <link rel="stylesheet" 
          href=
"https://unpkg.com/purecss@2.0.3/build/grids-responsive-min.css">
    <style>
    body {
        text-align: center;
    }

    .pure-u-1-1 {
        border: 5px solid green;
    }

    .pure-u-1-3 {
        background-color: aqua;
    }

    .pure-u-1-2 {
        background-color: blue;
    }

    .pure-u-1-1 {
        background-color: lightgreen;
    }
    </style>
</head>

<body>
    <div class="pure-g">
        <div class="pure-u-1-3">
            <p> First columns of the pure.css ||</p>

        </div>
        <div class="pure-u-1-2">
            <p> Second columns of the pure.css || </p>

        </div>
        <div class="pure-u-1-1">
            <p> GeeksforGeeks </p>

        </div>
        <div class="pure-u-1-1">
            <p>A computer science portal for geeks</p>

        </div>
    </div>
</body>

</html>
```

**输出:**从下面的输出中，我们可以看到，对于不同的窗口大小，内容不会因为设置到特定的设备宽度而受到影响。

![](img/52064334293b49f28751aea066133757.png)

设置不同的设备宽度