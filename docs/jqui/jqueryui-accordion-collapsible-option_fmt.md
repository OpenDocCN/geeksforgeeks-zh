# jQueryUI 手风琴可折叠选项

> 原文：[https://www.geeksforgeeks.org/jqueryui-accordion-collapsible-option/](https://www.geeksforgeeks.org/jqueryui-accordion-collapsible-option/)

`collapsible`选项允许用户通过单击关闭菜单。默认情况下，其值为`false`。

**取值：**

*   **布尔值：**如果设置为`true`，手风琴会折叠；如果设置为`false`，手风琴不会折叠。

### 方法

首先，添加项目所需的 jQuery Mobile 脚本。

> <script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/jquery-ui.js"></script>
> <link href="http://ajax.googleapis.com/ajax/libs/jqueryui/1.8.16/themes/ui-lightness/jquery-ui.css" rel="stylesheet" type="text/css" />

### 例子 1

#### HTML

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
                { collapsible : true }
            );
        }); 
    </script> 
    <style>
         #gfg{font-size: 17px;}
    </style>
</head>

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Collapsible Accordion</b> 
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

**输出：**

![](img/6a368b6764d3026cd3db4d50b7d83fa2.png)

### 例子 2

#### HTML

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
                   { collapsible : false }
            );
        }); 
    </script> 
    <style>
         #gfg{font-size: 17px;}
    </style>
</head>

<body> 
    <h1 style="color:green">GeeksforGeeks</h1> 
    <b>jQueryUI | Collapsible Accordion</b> 
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

**输出：**

![](img/5b5ce6b8aeb1bba676f533400323ae23.png)