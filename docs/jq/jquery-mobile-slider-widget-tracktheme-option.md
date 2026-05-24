# jQuery 移动滑块小部件轨迹主题选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-slider-widget-track theme-option/](https://www.geeksforgeeks.org/jquery-mobile-slider-widget-tracktheme-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery 移动滑块小部件轨迹主题选项来设置滑块轨迹的配色方案(样本)。可能的值介于(a-z)之间。它接受字符串类型值，默认值为 null，从父级继承而来。

**语法:**

```html
$( ".selector" ).slider({
    trackTheme: string
});
```

**CDN 链接:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 10 . 2 . min . js”></脚本>
> <脚本 src =//code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js”></脚本>

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">

    <script src="//code.jquery.com/jquery-1.10.2.min.js">
    </script>

    <script src=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("#GFG").slider({
                trackTheme: "b"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Slider Widget trackTheme Option</h3>
        </div>

        <div role="main" class="ui-content">
            <label for="slider">Input slider:</label>
            <input type="range" name="slider" id="GFG" 
                min="0" max="100" value="30">
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/872aec805a3ae9b00836c2a69cb47820.png)

**参考:**T2】https://api.jquerymobile.com/slider/#option-trackTheme