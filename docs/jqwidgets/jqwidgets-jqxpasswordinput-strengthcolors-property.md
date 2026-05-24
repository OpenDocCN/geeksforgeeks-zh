# jQWidgets jqxpassword input strengcolors 属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxpasswordpinput-strengcolors-property/](https://www.geeksforgeeks.org/jqwidgets-jqxpasswordinput-strengthcolors-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxPasswordInput 是一个 jQuery 小部件，它支持输入字段密码，并对密码的强度有很好的视觉反馈。

“强度颜色”属性用于设置显示密码强度的工具提示中使用的颜色。它接受对象类型值。

它的默认值–

```html
{ 
    tooShort: "rgb(170, 0, 51)", 
    weak: "rgb(170, 0, 51)", 
    fair: "rgb(255, 204, 51)", 
    good: "rgb(45, 152, 243)", 
    strong: "rgb(118, 194, 97)" 
}
```

**语法:**

```html
$('selector').jqxPasswordInput({ 
    strengthColors: { 
        tooShort: "Red", 
        weak: "Red", 
        fair: "Yellow", 
        good: "Blue", 
        strong: "Green" 
    } 
});
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets 中的 jqxPasswordInput strengthColors 属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxpasswordinput.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxPasswordInput strengthColors Property
        </h3>

        <input type="password" id="input" />
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#input").jqxPasswordInput({
                width: 250,
                height: 40,
                placeHolder: "Enter a Password",
                showStrength: true,
                strengthColors: {
                    tooShort: "rgb(204, 0, 0)",
                    weak: "rgb(255, 153, 0)",
                    fair: "rgb(255, 255, 0)",
                    good: "rgb(0, 0, 255)",
                    strong: "rgb(0, 102, 0)"
                }
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/755314a598ecd1e27873dc0855598d53.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxpasswordpinput/jquery-密码-输入-入门. htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxpasswordinput/jquery-password-input-getting-started.htm)