# jQuery 用户界面对话框可调整大小选项

> 原文:[https://www . geeksforgeeks . org/jquery-ui-dialog-resizable-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-resizable-option/)

*“可调整大小选项”*如果设置为 false，对话框将无法调整大小。默认情况下，值为真。

**语法:**

```html
$( ".selector" ).dialog({
  resizable: false
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
  <link rel = "stylesheet" href=
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
           resizable : false
        });
        $( "#geeks" ).click(function() {
           $( "#gfg" ).dialog( "open" );
        });
     });
  </script>
</head>

<body>
  <div id = "gfg" title = "GeeksforGeeks">
    Jquery UI| resizable dialog option
  </div>

  <button id = "geeks">
    Open Dialog
  </button>
</body>

</html>
```

**输出:**

![](img/20f19dbf34f3d4ee8f3a950d35c40dee.png)

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
           resizable : true
        });
        $( "#geeks" ).click(function() {
           $( "#gfg" ).dialog( "open" );
        });
     });
  </script>
</head>

<body>
  <div id = "gfg" title= "GeeksforGeeks">
    Jquery UI| resizable dialog option
  </div>

  <button id = "geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/bacb6095a09ad986018dfb5d764d3827.png)