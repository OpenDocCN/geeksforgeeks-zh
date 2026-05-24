# 如何使用 jQuery 手机广场-UI 主题插件为手机设计表单控件？

> 原文:[https://www . geesforgeks . org/how-design-form-controls-for-mobile-use-jquery-mobile-square-ui-theme-plugin/](https://www.geeksforgeeks.org/how-to-design-form-controls-for-mobiles-using-jquery-mobile-square-ui-theme-plugin/)

在本文中，我们将学习如何使用 **jQuery Mobile Square-UI 主题**插件为面向移动的应用程序设计表单控件。

**先决条件:**从给定的[链接](https://github.com/ququplay/jquery-mobile-square-ui-theme)下载预编译的所需库文件，并将其保存在您的工作文件夹中，以备后续实施。

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" content=
"width=device-width, initial-scale=1">

    <link rel="stylesheet" type="text/css" 
    href="css/jquery.mobile.squareui.css" />

    <script src="js/jquery.js"></script>
    <script src="js/jquery.mobile-1.4.0.min.js">
    </script>
</head>

<body>
    <h3>Example of buttons</h3>
    <div data-role="content" role="main">
        <fieldset class="ui-grid-a">
            <div class="ui-block-a">
                <button data-icon="flat-settings"
                    data-theme="a">
                    Button 1
                </button>
            </div>
            <div class="ui-block-b">
                <button data-icon="flat-new"
                    data-theme="b">
                    Button 2
                </button>
            </div>
            <div class="ui-block-a">
                <button data-icon="flat-man"
                    data-theme="c">
                    Button 3
                </button>
            </div>
            <div class="ui-block-b">
                <button data-icon="flat-mail"
                    data-theme="d">
                    Button 4
                </button>
            </div>
            <div class="ui-block-a">
                <button data-icon="flat-lock"
                    data-theme="e">
                    Button 5
                </button>
            </div>
            <div class="ui-block-b">
                <button data-icon="flat-menu"
                    data-theme="f">
                    Button 6
                </button>
            </div>
            <div class="ui-block-a">
                <button data-icon="flat-heart"
                    data-theme="g">
                    Button 7
                </button>
            </div>
        </fieldset>
    </div>
</body>

</html>
```