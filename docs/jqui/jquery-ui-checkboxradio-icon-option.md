# jquery ui check box radio icon option

> 原文:[https://www . geesforgeks . org/jquery-ui-checkbox radio-icon-option/](https://www.geeksforgeeks.org/jquery-ui-checkboxradio-icon-option/)

复选框单选小部件图标选项用于显示复选框或单选图标，具体取决于使用 jQuery 用户界面的输入类型。

**语法:**

```html
$( ".selector" ).checkboxradio({
  icon: false
});
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="”https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/themes/cupertino/jquery-ui.css”" rel="”stylesheet”">

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

                $(".radio, .checkbox").checkboxradio({
                    icon: false
                });
            }); 
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/7251565792694703c09ec0f104c8714c.png)