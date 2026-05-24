# jQuery UI 自动完成禁用选项

> 原文:[https://www . geesforgeks . org/jquery-ui-autocomplete-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-autocomplete-disabled-option/)

jQuery UI 自动完成禁用选项当设置为 true 时，将禁用菜单。默认值为**假**。

**语法:**

```html
$( ".selector" ).autocomplete({disabled: false}),
```

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
         $(function() {
            var list  =  [
               "One",
               "two",
               "Three",
               "Four",
            ];
            $( "#gfg" ).autocomplete({
               source: list,
               disabled:false
            });
         });
      </script>
   </head>

   <body>
      <div class = "ui-widget">
        <p>jQuery UI| disabled Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出:**

![](img/f57e8f60e24a7e03b8e97a0d456905c1.png)

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
         $(function() {
            var list  =  [
               "One",
               "two",
               "Three",
               "Four",
            ];
            $( "#gfg" ).autocomplete({
               source: list,
               disabled:true
            });
         });
      </script>
   </head>

   <body>
      <div class = "ui-widget">
        <p>jQuery UI| disabled Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出:**

![](img/a31ae7ca8d73127a14c68c3dd4f88a72.png)