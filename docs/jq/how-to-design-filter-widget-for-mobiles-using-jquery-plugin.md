# 如何使用 jQuery 插件为手机设计过滤小部件？

> 原文:[https://www . geeksforgeeks . org/how-design-filter-widget-for-mobiles-use-jquery-plugin/](https://www.geeksforgeeks.org/how-to-design-filter-widget-for-mobiles-using-jquery-plugin/)

在本文中，我们将学习如何使用 jQuery 过滤栏插件为移动应用程序的用户界面设计一个可过滤的小部件。该插件与许多 HTML 控件一起工作，如选择、按钮、表格、控件组。

从这个[链接](https://github.com/frequent/filterbar)下载所需的预编译文件，并保存在您的工作文件夹中，以实现以下示例。

**示例 1:** 以下示例演示了过滤器小部件。要创建过滤器功能，为 HTML 元素添加*数据过滤器=“真”*。在这种情况下，它是为“ul”元素完成的。插件的其他属性也可以根据需要设置。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <link rel="stylesheet" href="css.css" />

    <script src=
"http://code.jquery.com/jquery-1.9.1.min.js">
    </script>

    <script src="jqm.js"></script>
</head>

<body>
    <div data-role="page">
        <div data-role="content" id="divID">

            <p><strong>Listview images</strong></p>

            <div class="some">
                <ul data-role="listview" 
                    data-inset="true" data-filter="true" 
                    data-target="some"><br>
                    <li>
                        <img src="images/gfg2.JPG" 
                            alt="geeks1" 
                            data-filtertext="gfgFest" 
                            width="250" height="250">
                        gfgFest
                    </li>
                    <li>
                        <img src="images/gfg4.JPG" 
                            alt="geeks2" 
                            data-filtertext="fiesta" 
                            width="200" height="200">
                        fiesta
                    </li>
                    <li>
                        <img src="images/gfg6.PNG" 
                            alt="geeks3" 
                            data-filtertext="CS portal" 
                            width="200" height="200">
                        CS Portal
                    </li>
                    <li>
                        <img src="images/background2.JPG" 
                            alt="geeks4" 
                            data-filtertext="html" 
                            width="200" height="200">
                        html
                    </li>
                    <li>
                        <img src="images/background3.JPG" 
                            alt="geeks5" 
                            data-filtertext="css" 
                            width="200" height="200">
                        css
                    </li>
                </ul>
            </div>
            <!-- End div content -->
        </div>
        <!-- End div page -->
    </div>
</body>

</html>
```