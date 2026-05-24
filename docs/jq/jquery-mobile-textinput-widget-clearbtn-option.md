# jquery mobile textinput widget clearbtn 选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-mobile-textinput 小部件-clearbtn 选项/

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Textinput Widget clear BTN 选项在输入元素设置为 true 时向其添加一个清除按钮。

**语法:**

```html
$( ".selector" ).textinput({
    clearBtn: boolean
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
                clearBtn: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Textinput Widget clearBtn Option</h3>
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

![](img/17e6bdcc1576416e62848e61a8c2ad4d.png)

**参考:**[https://API . jquerymobile . com/textinput/# option-clearbtn](https://api.jquerymobile.com/textinput/#option-clearBtn)