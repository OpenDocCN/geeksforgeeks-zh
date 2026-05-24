# jQuery UI 自动完成 minLength 选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-autocompute-minlength 选项/

jQuery UI 自动完成最小长度选项设置输入字段中应输入的最小字符数。默认值为 **0**

**语法:**

```html
$( ".selector" ).autocomplete({minLength: 1}),
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
               minLength: 1
            });
         });
      </script>
   </head>

   <body>
      <div class = "ui-widget">
        <p>jQuery UI| minLength Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出:**

![](img/e1fc5257948b2eb50b0c27de7375e3e7.png)

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
               minLength: 2
            });
         });
      </script>
   </head>

   <body>
      <div class = "ui-widget">
        <p>jQuery UI| minLength Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出:**

![](img/406c8510a05adca928971a38305adc41.png)