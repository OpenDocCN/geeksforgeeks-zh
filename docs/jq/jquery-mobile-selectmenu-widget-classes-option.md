# jquery mobile select menu widget 类别选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-mobile-selectmenu widget-classes 选项/

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。
在本文中，我们将使用 jQuery Mobile Selectmenu Widget 类选项向元素中添加一些额外的类。附加类可用于将样式添加到 selectmenu。它接受对象类型值。

**语法:**

```html
$( ".selector" ).selectmenu({
  classes: {
    "ui-selectmenu": "highlight"
  }
});
```

**CDN 链接:**首先，添加项目所需的 jQuery Mobile 脚本。

> <脚本 src = "//code . jquery . com/jquery-3 . 2 . 1min . js "></脚本><脚本 src = "//code . jquery . com/mobile/1 . 5 . 0-alpha . 1/jquery . mobile-1 . 5 . 0-alpha

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
"//code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.css">
    <script src="//code.jquery.com/jquery-3.2.1.min.js"></script>
    <script src=
"//code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.js">
    </script>

    <style>
        .highlight {
            border: 5px solid green;
        }
    </style>

    <script>
        $(document).ready(function () {
            $("#GFG").selectmenu({
                classes: {
                    "ui-selectmenu": "highlight"
                }
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <center>
            <div data-role="header">
                <h1>GeeksforGeeks</h1>
                <h3>jQuery Mobile Selectmenu Widget classes Option</h3>
            </div>
        </center>

        <div role="main" class="ui-content">
            <label for="GFG" class="select">
                GeeksforGeeks Courses:
            </label>
            <select name="GFG" id="GFG">
                <option value="C">C Programming</option>
                <option value="CPP">C++ Programming</option>
                <option value="JAVA">Java Programming</option>
                <option value="overnight">Python Programming</option>
                <option value="WEB">Web Development</option>
            </select>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/eb09220682f56533029ceb8f17ef4929.png)

**参考:**[https://API . jquerymobile . com/select menu/# option-classes](https://api.jquerymobile.com/selectmenu/#option-classes)