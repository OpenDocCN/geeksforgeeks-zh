# 如何销毁 jQuery UI 中的一个按钮？

> 原文:[https://www . geesforgeks . org/how-to-destroy-a-button-in-jquery-ui/](https://www.geeksforgeeks.org/how-to-destroy-a-button-in-jquery-ui/)

要销毁 jQuery 用户界面中的按钮，我们将使用下面讨论的销毁()方法:

jQuery UI destroy()方法用于移除按钮的完整功能。它将按钮元素完全返回到其初始状态。

**语法:**

```html
$(".selector").button("destroy")
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
            $("#buttonId, #submitId, #anchorId").button();

            $('#buttonId, #submitId, #anchorId')
                .click(function (event) {

                event.preventDefault(); 
                $(this).button("destroy"); 
            }); 
        }); 
    </script> 
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Button destroy Method</b> 
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

*![](img/e7555e9f4afec0cbab29f447c10f439c.png)*

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
            $("#buttonId").button();

            $('#buttonId').click(function (event) { 
                event.preventDefault(); 
                $(this).button("destroy"); 
                console.log("The button is destroyed succesfully")
            }); 
        }); 
    </script> 
</head> 

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Button destroy Method</b> 
    <div class="height"> </div><br> 
    <button id="buttonId">Button element</button> 
</body> 

</html>*
```

***输出:***

*![](img/eb152242037c301f52ecea84caec7083.png)*

***参考:**[https://API . jquery ui . com/button/](https://api.jqueryui.com/button/)*