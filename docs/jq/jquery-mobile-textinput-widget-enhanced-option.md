# jQuery 手机文本输入小工具增强选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-text input-widget-enhanced-option/](https://www.geeksforgeeks.org/jquery-mobile-textinput-widget-enhanced-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Textinput Widget 增强选项，该选项描述了作为原始标记的一部分提供的 Textinput Widget 所需的标记。

**语法:**

```html
$( ".selector" ).textinput({
    enhanced: boolean
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
            $("#GFG").textinput({
                enhanced: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Textinput Widget enhanced Option</h3>
        </div>

        <center>
            <div role="main" class="ui-content" style="width: 50%;">
                <label for="GFG">Enter Text:</label>
                <input type="text" name="Geeks" id="GFG" value="">
            </div>
        </center>
    </div>
</body>

</html>
```

**输出:**

![](img/e3fc683b5f73344c6993e0d9ea7e6ed6.png)

**参考:**T2】https://api.jquerymobile.com/textinput/#option-enhanced