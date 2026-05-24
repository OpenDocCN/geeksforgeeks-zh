# jQuery 移动 Checkboxradio 小部件包装类选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-checkbox radio-widget-wrapperclass-option/](https://www.geeksforgeeks.org/jquery-mobile-checkboxradio-widget-wrapperclass-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile checkbox radio Widget wrapper class Option 来指定一个或多个要由框架添加到包装器 div 元素中的以空格分隔的类名。它的默认值为 null。

**语法:**

```html
$( ".selector" ).checkboxradio({
    wrapperClass: string
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
    <meta name="viewport" 
        content="width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">

    <script src=
        "//code.jquery.com/jquery-1.10.2.min.js">
    </script>

    <script src=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>

    <style>
        .Geeks {
            border: 2px solid green;
        }
    </style>

    <script>
        $(document).ready(function () {
            $(".GFG, .GFG1").checkboxradio({
                wrapperClass: "Geeks"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Checkboxradio Widget wrapperClass Option</h3>
        </div>

        <div role="main" class="ui-content">
            <div class="ui-field-contain">
                <form>
                    <fieldset data-role="controlgroup">
                        <legend>Are you a student:</legend>
                        <input type="checkbox" name="checkbox" 
                            id="checkbox" class="GFG">
                        <label for="checkbox">I agree</label>
                    </fieldset>

                    <br>
                    <fieldset data-role="controlgroup">
                        <legend>Course:</legend>
                        <input type="radio" name="radioBtn" 
                            id="radioBtn1" class="GFG1" checked="checked">
                        <label for="radioBtn1">B. Tech</label>

                        <input type="radio" name="radioBtn" 
                            id="radioBtn2" class="GFG1">
                        <label for="radioBtn2">M. Tech</label>

                        <input type="radio" name="radioBtn" 
                            id="radioBtn3" class="GFG1">
                        <label for="radioBtn3">Others</label>
                    </fieldset>
                </form>
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/d9505516b8d78a1420258f8eac012db0.png)

**参考:**[https://API . jquerymobile . com/1.4/checkbox radio/# option-wrapper class](https://api.jquerymobile.com/1.4/checkboxradio/#option-wrapperClass)