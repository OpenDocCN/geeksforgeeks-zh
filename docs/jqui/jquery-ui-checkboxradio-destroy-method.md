# jQuery UI Checkboxradio 销毁()方法

> 原文:[https://www . geesforgeks . org/jquery-ui-checkbox radio-destroy-method/](https://www.geeksforgeeks.org/jquery-ui-checkboxradio-destroy-method/)

Checkboxradio Widget destroy()方法用于删除 Checkboxradio 按钮的所有功能。它将元素返回到初始化前的状态。此方法不接受任何参数。

**语法:**

```html
$( ".selector" ).checkboxradio( "destroy" );
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link href=
'https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/themes/cupertino/jquery-ui.css'
        rel='stylesheet'>

    <script src=
        "https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js">
    </script>

    <script src=
        "https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>

        <h3>Radio Button Example</h3>
        <label for="radio1">Button 1</label>
        <input type="radio" name="radio" 
            id="radio1" class='radio'>
        <br>

        <label for="radio2">Button 2</label>
        <input type="radio" name="radio" 
            id="radio2" class='radio'>
        <br>

        <label for="radio3">Button 3</label>
        <input type="radio" name="radio" 
            id="radio3" class='radio'>
        <br><br><br>

        <h3>Checkbox Example</h3>
        <label for="checkbox1">Checkbox 1</label>
        <input type="checkbox" name="checkbox1" 
            id="checkbox1" class='checkbox'>
        <br>

        <label for="checkbox2">checkbox 2</label>
        <input type="checkbox" name="checkbox2" 
            id="checkbox2" class='checkbox'>

        <script>
            $(document).ready(function () {

                $(".radio, .checkbox").checkboxradio({"destroy"});
            }); 
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/e53f9bcfcecdde0001dfd46c3cde7a29.png)