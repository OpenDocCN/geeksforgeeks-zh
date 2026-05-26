# jQueryUI 手风琴激活选项

> 原文:[https://www . geeksforgeeks . org/jqueryui-accordion-active-option/](https://www.geeksforgeeks.org/jqueryui-accordion-active-option/)

折叠激活选项指示当页面被访问时，折叠菜单的哪个索引将被打开。默认情况下，该值为 **0** ，即第一个菜单面板。

**价值观:**

*   **布尔:**设置为假时会折叠所有面板。
*   **整数:**从零开始的索引，用于设置哪个面板处于活动状态。值也可以是负数。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <src 脚本= " https://Ajax . Google APIs . com/Ajax/libs/jquery/1 . 7 . 1/jquery . js "></script><src 脚本= " https://Ajax . Google APIs . com/Ajax/libs/jquery ui/1.8

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
                   { active: 1 }
            );
        }); 
    </script> 
    <style>
         #gfg{font-size: 17px;}
    </style>
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Active Accordion</b> 
    <br>
    <br>
    <div id="gfg">
        <h3>GFG</h3>
        <div>GeeksforGeeks</div>
        <h3>Geeks</h3>
        <div>GeeksforGeeks</div>
    </div> 
</body> 

</html>
```

**输出:**

![](img/03f64f1649abf48e514712cd4c9ea38a.png)

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
      rel="stylesheet" type="text/css"/>

    <style> 
        .height { 
            height: 10px; 
        } 
    </style> 

    <script> 
        $(function () { 
            $( "#gfg" ).accordion(
                   { active: false }
            );        
        }); 
    </script> 

    <style>
         #gfg{font-size: 17px;}
    </style>
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Active Accordion</b> 
    <br>
    <br>
    <div id="gfg">
        <h3>A</h3>
        <div>A</div>
        <h3>B</h3>
        <div>B</div>
        <h3>C</h3>
        <div>C</div>
    </div> 
</body> 

</html>
```

**输出:**

![](img/8c3a345259449803ab0aad809ce30f09.png)