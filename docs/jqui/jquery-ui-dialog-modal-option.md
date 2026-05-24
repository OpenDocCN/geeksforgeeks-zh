# jQuery 用户界面对话框模态选项

> 原文:[https://www . geesforgeks . org/jquery-ui-dialog-modal-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-modal-option/)

*“模态选项”*如果设置为真，将禁用对话框中的其他项目。默认情况下，值为 false。

**语法:**

```html
$( ".selector" ).dialog({
  modal: false
});
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**例 1:**

## 超文本标记语言

```html
<!doctype html>                                             
<html lang = "en">

<head>
  <meta charset = "utf-8">
  <link rel = "stylesheet" href =
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css">

  <script src =
"https://code.jquery.com/jquery-1.10.2.js">
  </script>

  <script src =
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
  </script>

  <script>
     $(function() {
        $( "#gfg" ).dialog({
           autoOpen: false,
           modal : true
        });
        $( "#geeks" ).click(function() {
           $( "#gfg" ).dialog( "open" );
        });
     });
  </script>
</head>

<body>
  <div id = "gfg" title = "GeeksforGeeks">
    Jquery UI| modal dialog option
  </div>

  <button id = "geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/eb75b3938ef378c5664e84c2cdab1dbc.png)

**例 2:**

## 超文本标记语言

```html
<!doctype html>                                             
<html lang = "en">

<head>
  <meta charset = "utf-8">
  <link rel = "stylesheet" href =
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css">

  <script src =
"https://code.jquery.com/jquery-1.10.2.js">
  </script>

  <script src =
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
  </script>

  <script>
     $(function() {
        $( "#gfg" ).dialog({
           autoOpen: false,
           modal : false
        });
        $( "#geeks" ).click(function() {
           $( "#gfg" ).dialog( "open" );
        });
     });
  </script>
</head>

<body>
  <div id = "gfg" title ="GeeksforGeeks">
    Jquery UI| modal dialog option
  </div>

  <button id = "geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/c01cb620e09ea59d38a7a40a872d8e56.png)