# 如何在 jQuery UI 中禁用一个按钮？

> 原文:[https://www . geesforgeks . org/如何禁用 jquery-ui 中的按钮/](https://www.geeksforgeeks.org/how-to-disable-a-button-in-jquery-ui/)

要禁用 jQuery 用户界面中的按钮，我们将使用 disable()方法，该方法将在下面讨论:

jQuery UI disable()方法用于完全禁用按钮。它将按钮元素完全返回到其初始状态。

**语法:**

```html
$(".selector").button("disable")
```

**参数:**此方法不接受任何参数。

**返回值:** 这个方法只是将按钮返回到初始状态。

*   **jQuery 用户界面库的链接:**

> <链接 rel=样式表’
> *【href = " http://Ajax . Google APIs . com/Ajax/libs/jqueryui/1 . 8 . 16/themes/ui-light/jquery-ui . CSS ">*

*   ***或***

> *<链接 rel=样式表’
> *href = " https://code . jquery . com/ui/1 . 10 . 4/themes/ui-lightness/jquery-ui . CSS ">
> <脚本 src = " https://"**

*下面是显示此方法实现的示例。*

***例 1:***

## *超文本标记语言*

```html
*<!DOCTYPE html> 
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
            $("#buttonId").button();

            $('#buttonId').click(function (event) { 
                event.preventDefault(); 
                $(this).button("disable"); 
                console.log("The button is disabled successfully")
            }); 
        }); 
    </script> 
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Button disable Method</b> 
    <div class="height"> </div><br> 
    <button id="buttonId">Button element</button> 
</body> 

</html>*
```

***输出:***

*![](img/58e449b6e5a3d9605fc66d0e0b105ffd.png)*

***例 2:***

## *超文本标记语言*

```html
*<!DOCTYPE html> 
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
            $("#buttonId, #submitId, #anchorId").button();

            $('#buttonId, #submitId, #anchorId')
                .click(function (event) { 
                event.preventDefault(); 
                $(this).button("disable"); 
            }); 
        }); 
    </script> 
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Button disable Method</b> 
    <div class="height"> </div><br> 
    <div class="buttons-div"> 
        <button id="buttonId">Button element</button> 
        <input id="submitId" type="submit" 
            value="Submit button"> 
        <a id="anchorId" href="">Anchor</a> 
    </div> 
</body> 

</html>*
```

***输出:***

*![](img/ac4f43063e46ac25432bbbf1dbc64022.png)*

***参考:**[https://API . jquery ui . com/button/](https://api.jqueryui.com/button/)*