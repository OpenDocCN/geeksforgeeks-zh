# jquery ui date picker button image option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-date picker-button image 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 日期选择器按钮图像选项用于设置弹出按钮图像的网址。如果我们设置按钮图像，那么它将显示它，否则显示替代文本。

**语法:**

```html
$( ".selector" ).datepicker({
  buttonImage: "datepicker.png"
});
```

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 12 . 4 . js "></脚本>
> <脚本 src =//code . jquery . com/ui/1 . 12 . 1/jquery-ui . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet" />
    <script src="https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <!-- Javascript -->
    <script>
        $(function () {
            $("#gfg").datepicker({
                showOn: "both",
                buttonImage: 
"https://media.geeksforgeeks.org/wp-content/uploads/20210314172651/cal.png",
                buttonImageOnly: true
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI datepicker buttonImage Option</h3>

    <div>Enter Date: <input type="text" id="gfg" /></div>
</body>

</html>
```

**输出:**

![](img/d634adb6de04452f425fd59ed2192711.png)

**参考:**[https://API . jquery ui . com/date picker/# option-button image](https://api.jqueryui.com/datepicker/#option-buttonImage)