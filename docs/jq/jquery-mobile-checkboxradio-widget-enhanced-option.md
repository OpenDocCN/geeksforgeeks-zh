# jQuery 手机 Checkboxradio 小工具增强选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-checkbox radio-widget-enhanced-option/](https://www.geeksforgeeks.org/jquery-mobile-checkboxradio-widget-enhanced-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。
在本文中，我们将使用 jQuery Mobile Checkboxradio 小部件*增强的*选项，该选项指示作为原始标记的一部分提供的 Checkboxradio 小部件所需的标记。它接受布尔类型值，默认值为*假*。

**语法:**

```html
$( ".selector" ).checkboxradio({
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

    <script>
        $(document).ready(function () {
            $(".GFG, .GFG1").checkboxradio({
                enhanced: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Checkboxradio Widget enhanced Option</h3>
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

![](img/845ea3fb8b52025ca31a81f22c124438.png)

**参考:**T2【https://API . jquerymobile . com/1.4/checkbox radio/# option-enhanced