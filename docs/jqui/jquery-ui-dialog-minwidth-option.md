# jQuery 用户界面对话框最小宽度选项

> 原文:[https://www . geeksforgeeks . org/jquery-ui-dialog-min width-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-minwidth-option/)

**对话框最小宽度**选项用于设置对话框可以设置的最小宽度，以像素为单位。默认情况下，该值为 150。

**语法:**

```html
$( ".selector" ).dialog({
  minWidth : 150
});
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="”https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" 
        rel="stylesheet">
  <script src=
"https://code.jquery.com/jquery-1.10.2.js">
  </script>
  <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
  </script>
  <script>
    $(function () {
      $("#gfg").dialog({
        autoOpen: false,
        minWidth: 150
      });

      $("#geeks").click(function () {
        $("#gfg").dialog("open");
      });
    });
  </script>
</head>
<body>
  <div id="gfg">
    Jquery UI| minWidth dialog option
  </div>
  <button id="geeks">Open Dialog</button>
</body>
</html>
```

**输出:**

![](img/7b1484f953a8de9086491650df77227b.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">
  <script src=
"https://code.jquery.com/jquery-1.10.2.js">
  </script>
  <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
  </script>
  <script>
    $(function () {
      $("#gfg").dialog({
        autoOpen: true,
        minWidth: 500
      });
    });
  </script>
</head>
<body>
  <div id="gfg">
    Jquery UI| minWidth dialog option
  </div>
</body>
</html>
```

**输出:**

![](img/206ab57e9ece27c4a3df37658502b5c0.png)