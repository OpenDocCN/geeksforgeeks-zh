# 如何使用 jQuery Mobile 创建没有输入区域的全幅滑块？

> 原文:[https://www . geeksforgeeks . org/如何使用 jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-full-width-slider-without-input-area-using-jquery-mobile/) 创建全宽无输入区域滑块

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应性内容。在本文中，我们将使用 **jQuery Mobile** 创建一个没有输入区域的全宽滑块。

**方法:**添加项目所需的 jQuery 移动脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个没有输入区域的全幅滑块。滑块是使用滑块插入数据的输入类型。我们用 *type="range"* 属性配合 *<输入>* 元素创建一个滑块。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src=
        "http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>

    <style>
        /* Hide the number input */
        .full-width-slider input {
            display: none;
        }

        .full-width-slider .ui-slider-track {
            margin-left: 15px;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <h4>
            Design a Full width slider without
            input area using jQuery Mobile
        </h4>

        <form class="full-width-slider" style="width: 50%;">
            <label for="slider" class="ui-hidden-accessible">
                Full width slider without input area:
            </label>

            <input type="range" name="slider" id="slider"
                data-track-theme="b" data-mini="true" 
                data-theme="b" min="0" max="100" value="50">
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/dded5501aa42027bfac1e7558e6ea03b.png)