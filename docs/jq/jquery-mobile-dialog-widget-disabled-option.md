# jQuery 移动对话框小部件禁用选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-dialog-widget-disabled-option/](https://www.geeksforgeeks.org/jquery-mobile-dialog-widget-disabled-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。
在本文中，我们将使用 jQuery 移动对话框小部件*禁用*选项来禁用对话框，如果其值设置为*真*。

**语法:**

```html
$( ".selector" ).dialog({
    disabled: boolean
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
            $("#GFG").dialog({
                disabled: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Dialog Widget disabled Option</h3>
        </div>

        <div role="main" class="ui-content">
            <center><a href="#GFG" data-rel="dialog">Open dialog</a>
            </center>
        </div>
    </div>

    <div data-role="page" id="GFG">
        <div data-role="header">
            <h2>GeeksforGeeks</h2>
        </div>
        <div role="main" class="ui-content">

<p>A computer science portal</p>

        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/3f1c782ea22d17120265beeec1ba4a8d.png)

**参考:**T2】https://api.jquerymobile.com/dialog/#option-disabled