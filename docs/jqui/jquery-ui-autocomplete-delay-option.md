# jQuery UI 自动完成延迟选项

> 原文:[https://www . geesforgeks . org/jquery-ui-自动完成-延迟-选项/](https://www.geeksforgeeks.org/jquery-ui-autocomplete-delay-option/)

jQuery UI 自动完成延迟选项用于设置建议显示给用户的时间。默认值为 300。

**语法:**

```html
$( ".selector" ).autocomplete({delay: 300})
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
               delay:300
            });
         });
      </script>
   </head>

   <body>
      <div class = "ui-widget"> 
        <p>jQuery UI| delay Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出:**

![](img/fdf6472f642ea62d3ac494291d32b0bf.png)

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
               delay:700
            });
         });
      </script>
   </head>

   <body>
      <div class = "ui-widget">
        <p>jQuery UI| delay Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出:**

![](img/3e830a2b72028b9d9a353111412f76e2.png)