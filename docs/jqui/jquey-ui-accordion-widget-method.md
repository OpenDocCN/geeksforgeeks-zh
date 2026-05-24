# jQuery UI 手风琴小部件()方法

> 原文:[https://www . geesforgeks . org/jquey-ui-accordion-widget-method/](https://www.geeksforgeeks.org/jquey-ui-accordion-widget-method/)

jQuery UI 小部件()方法用于返回当前 jQuery 手风琴元素的实例。

**语法:**

```html
var a = $( ".selector" ).accordion( "enable" )
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法 r 返回当前 jQuery 手风琴元素的实例。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link href="”http://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/themes/ui-lightness/jquery-ui.css”" rel="”stylesheet”" type="”text/css”">

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.js">
    </script>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/jquery-ui.js">
    </script>

    <link href=
"http://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet" type="text/css" />

    <style>
        .height {
            height: 10px;
        }
    </style>

    <script>
        $(function () {
            $( "#gfg" ).accordion();
            var a = $( "#gfg" ).accordion( "widget" );
            console.log(a)
        });
    </script>
    <style>
         #gfg{font-size: 17px;}
    </style>
</head>

<body>
    <h1 style="color:green">GeeksforGeeks</h1>
    <b>jQueryUI | widget Accordion</b>
    <br>
    <br>
    <div id="gfg">
        <h2>A</h2>
         <div>Geeks1
            <br>Geeks1
            <br>Geeks1
            <br>Geeks1
            <br>
        </div>
        <h2>B</h2>
        <div>Geeks2
            <br>Geeks2
            <br>Geeks2
            <br>Geeks2
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/efde1bb657a2d1dd0b6b86c246cf49c3.png)