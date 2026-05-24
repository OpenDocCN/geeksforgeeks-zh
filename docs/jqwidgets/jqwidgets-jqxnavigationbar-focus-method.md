# jQWidgets jqxNavigationBar 焦点()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnavigationbar-focus-method/](https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-focus-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxNavigationBar** 用于表示包含标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。

**聚焦()**方法用于聚焦指定的 jqxNavigationBar。当 jqxNavigationBar 小部件被聚焦时，就可以使用键盘进行导航。

**以下是 jqxNavigationBar 支持的一些按键及其功能:**

*   **回车/空格键:**用于折叠或展开项目。
*   **左/上箭头:**用于聚焦前一个项目标题，如果当前聚焦的是第一个，则聚焦最后一个项目标题。
*   **向右/向下箭头:**用于聚焦下一个项目标题，如果当前聚焦的是最后一个，则聚焦第一个项目标题。
*   **结束:**这集中在最后一个项目头。
*   **首页:**这集中在第一个项目表头。
*   **Tab:** 用于聚焦 DOM 中的第一个头或下一个元素。
*   **Ctrl+向上箭头:**如果焦点在某个项目内容上，则聚焦在其各自的标题上。
*   **Ctrl+向下箭头:**如果焦点在一个项目标题上，则聚焦在它各自的内容上。

**语法:**

```html
$('Selector').jqxNavigationBar('focus');
```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**链接文件:**从给定链接下载https://www.jqwidgets.com/download/。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><

**示例:**下面的示例说明了 jQWidgets jqxNavigationBar***focus()***方法。在下面的例子中，借助 ***focus()*** 的方法，导航栏已经被聚焦。然后使用“向下箭头”和“输入”按钮展开第二个项目。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css"
          type="text/css"/>
    <script type="text/javascript" 
            src="scripts/jquery.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxexpander.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxnavigationbar.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxNavigationBar focus() Method
        </h3>
        <div id="jqx_Navigation_Bar" style="margin: 25px;"
            align="left">

            <div>First Header</div>
            <div>
                <h8>Content for the first header</h8>
                <ul>
                    <li>GFG</li>
                    <li>CSE</li>
                </ul>
            </div>
            <div> Second Header</div>
            <div>
                <h8>Content for the second header</h8>
                <ul>
                    <li>GeeksforGeeks</li>
                    <li>CSE</li>
                </ul>
            </div>
        </div>
        <input type="button" style="margin: 29px;" 
           id="jqxbutton_for_focus" 
           value="Focus the above NavigationBar" />

        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 290,
                        height: 150,
                    });
                $("#jqxbutton_for_focus").
                    jqxButton({
                        width: 250,
                    });
                $('#jqxbutton_for_focus').
                    on('click', function () {
                        $('#jqx_Navigation_Bar').
                            jqxNavigationBar(
                                'focus');
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/e322ce45352b63fb5a0678424e55c2d8.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm?search=)