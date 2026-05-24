# jQueryUI 手风琴头选项

> 原文:[https://www . geeksforgeeks . org/jqueryui-accordion-header-option/](https://www.geeksforgeeks.org/jqueryui-accordion-header-option/)

在本文中，我们将看到如何在手风琴中使用标题选项。标题选项用于设置将用作手风琴标题菜单的标签。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <src 脚本= " https://Ajax . Google APIs . com/Ajax/libs/jquery ui/1 . 8 . 16/jquery-ui . js "></script><link href = " http://Ajax . Google APIs . com/Ajax

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
            $( "#gfg" ).accordion(
                { header : "h2" }
            );
        }); 
    </script> 
    <style>
         #gfg{font-size: 17px;}
    </style>
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | header Accordion</b> 
    <br>
    <br>
    <div id="gfg">
        <h2>GFG</h2>
        <div>GeeksforGeeks</div>
        <h2>Geeks</h2>
        <div>GeeksforGeeks</div>
    </div> 
</body> 

</html>
```

**输出:**

![](img/ca8ef7e4edfec409a65a6f72070f54e9.png)

**例 2:**

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
            $( "#gfg" ).accordion(
                { header : "h7" }
            );
        });
    </script> 
    <style>
         #gfg{font-size: 17px;}
    </style>
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | header Accordion</b> 
    <br>
    <br>
    <div id="gfg">
        <h7>GFG</h7>
        <div>GeeksforGeeks</div>
        <h7>Geeks</h7>
        <div>GeeksforGeeks</div>
    </div> 
</body> 

</html
```

**输出:**

![](img/d85d74a2cb5761120b7afdcb6efcd898.png)