# jQueryUI 手风琴禁用选项

> 原文:[https://www . geesforgeks . org/jqueryui-accordo-disabled-option/](https://www.geeksforgeeks.org/jqueryui-accordion-disabled-option/)

禁用选项允许用户禁用菜单。默认情况下，该值为**假**

**值:**

*   **布尔值:**如果设置为真，手风琴将被禁用，如果设置为假，手风琴将不会被禁用。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <src = " https://Ajax . Google APIs . com/Ajax/libs/jquery ui/1 . 8 . 16/jquery-ui . js "></script><link href = " http://Ajax . Google APIs . com/Ajax

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
                   { disabled : false }
            );
        });
    </script>
    <style>
         #gfg{font-size: 17px;}
    </style>
</head>

<body>
    <h1 style="color:green">GeeksforGeeks</h1>
    <b>jQueryUI | disabled Accordion</b>
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

![](img/2e921bdf90fa44ec4e2e3b417f99745d.png)

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
        $(function () {
            $( "#gfg" ).accordion(
                { disabled : true }
            );
        });
    </script>
    <style>
         #gfg{font-size: 17px;}
    </style>
</head>

<body>
    <h1 style="color:green">GeeksforGeeks</h1>
    <b>jQueryUI | disabled Accordion</b>
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

![](img/676780da180017f0ab9142ea5fc8b9d0.png)