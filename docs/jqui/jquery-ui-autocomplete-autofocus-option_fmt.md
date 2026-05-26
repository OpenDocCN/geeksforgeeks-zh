# jQuery UI 自动完成自动对焦选项

> 原文：[https://www.geeksforgeeks.org/jquery-ui-autocomplete-autofocus-option/](https://www.geeksforgeeks.org/jquery-ui-autocomplete-autofocus-option/)

在本文中，我们将讨论 JqueryUI 中的自动完成自动对焦选项。jQuery UI 自动完成 `autoFocus` 选项当设置为 `true` 时，当菜单显示时，第一个项目将自动对焦。默认值为 `false`。

## 语法

```html
$( ".selector" ).autocomplete({autoFocus: true}),
```

## 方法

首先，添加项目所需的 jQuery Mobile 脚本。

```html
<script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/jquery-ui.js"></script>
<link href="http://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/themes/ui-lightness/jquery-ui.css" rel="stylesheet" type="text/css" />
```

### 例 1

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
            var list = [
               "One",
               "two",
               "Three",
               "Four",
            ];
            $( "#gfg" ).autocomplete({
               source: list,
               autoFocus:false
            });
         });
      </script>
   </head>

<body>
      <div class = "ui-widget">
        <p>jQuery UI| autoFocus Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出：**

![](img/d41343fbe00b0a8865b95a26ddef327b.png)

### 例 2

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
            var list = [
               "One",
               "two",
               "Three",
               "Four",
            ];
            $( "#gfg" ).autocomplete({
               source: list,
               autoFocus:true
            });
         });
      </script>
   </head>

<body>
      <div class = "ui-widget">
        <p>jQuery UI| autoFocus Element</p>
        <p>GeeksforGeeks</p>
        <label for = "gfg">Tags: </label>
        <input id = "gfg">
      </div>
   </body>
</html>
```

**输出：**

![](img/502982d57f943339f6cdb08ffcf2fab9.png)