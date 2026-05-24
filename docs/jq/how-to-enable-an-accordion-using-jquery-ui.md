# 如何使用 jQuery UI 启用手风琴？

> 原文:[https://www . geeksforgeeks . org/如何启用手风琴-使用-jquery-ui/](https://www.geeksforgeeks.org/how-to-enable-an-accordion-using-jquery-ui/)

在本文中，我们将看到如何在 JqueryUI 中启用手风琴。要在 jQuery 用户界面中启用折叠，我们将使用 enable()方法。jQuery UI enable()方法用于启用手风琴，并将手风琴元素完全返回到其初始状态。

**语法:**

```html
$( ".selector" ).accordion( "enable" )
```

**参数:**此方法不接受任何参数。

**返回值:**该方法只是将按钮返回到其初始前的状态。

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <src 脚本= " https://Ajax . Google APIs . com/Ajax/libs/jquery ui/1 . 8 . 16/jquery-ui . js "></script><link href = " http://Ajax . Google APIs . com/Ajax

**示例:**

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
            $( "#gfg" ).accordion( "enable" );
        }); 
    </script> 
    <style>
         #gfg{font-size: 17px;}
    </style>
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | enable Accordion</b> 
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

![](img/b70e0795039d4ca6bc81f93cecf56454.png)