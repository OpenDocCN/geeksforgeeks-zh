# jQuery 移动滑块小部件主题选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-slider-widget-theme-option/](https://www.geeksforgeeks.org/jquery-mobile-slider-widget-theme-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Slider Widget 主题选项来设置 Slider Widget 的配色方案(样本)。主题值使用单个字母 a-z。它接受字符串类型值，默认值为空，从父级继承而来。

**语法:**

```html
$( ".selector" ).slider({
    theme: string
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
                theme: "b"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>
             jQuery Mobile Slider Widget theme Option
            </h3>
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

![](img/cc985c25371690621d0ebdd70a551fbf.png)

**参考:**T2】https://api.jquerymobile.com/slider/#option-theme