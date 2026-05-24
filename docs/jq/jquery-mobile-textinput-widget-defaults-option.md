# jQuery 手机文本输入小部件默认选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-text input-widget-defaults-option/](https://www.geeksforgeeks.org/jquery-mobile-textinput-widget-defaults-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Textinput Widget 默认值 Option，并将其值设置为 true，表示其他 Widget 选项具有默认值，这将导致自动增强代码省略从数据属性中检索选项值的步骤。

**语法:**

```html
$( ".selector" ).textinput({
    defaults: boolean
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
                defaults: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Textinput Widget defaults Option</h3>
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

![](img/417101219bb3a619d9dccfab6ab72e23.png)

**参考:**[https://API . jquerymobile . com/textinput/# option-defaults](https://api.jquerymobile.com/textinput/#option-defaults)