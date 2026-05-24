# jquery mobile textinput widget autorow option

> 原文:[https://www . geesforgeks . org/jquery-mobile-text input-widget-auto grow-option/](https://www.geeksforgeeks.org/jquery-mobile-textinput-widget-autogrow-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery 移动文本输入小部件自动增长选项来更新文本区域元素的大小。textarea 的大小根据内容元素而变化。此选项用于 textarea 元素。

**语法:**

```html
$( ".selector" ).textinput({
    autogrow: boolean
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
                autogrow: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Textinput Widget autogrow Option</h3>
        </div>

        <center>
            <div role="main" class="ui-content" style="width: 50%;">
                <label for="GFG">Enter Text:</label>
                <textarea name="Geeks" id="GFG"></textarea>
            </div>
        </center>
    </div>
</body>

</html>
```

**输出:**

![](img/c8bea24283540425b3fa35458036b684.png)

**参考:**[https://API . jquerymobile . com/textinput/# option-autorow](https://api.jquerymobile.com/textinput/#option-autogrow)