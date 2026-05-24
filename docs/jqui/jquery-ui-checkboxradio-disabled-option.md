# jQuery UI 复选框单选禁用选项

> 原文:[https://www . geesforgeks . org/jquery-ui-checkbox radio-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-checkboxradio-disabled-option/)

复选框单选小部件禁用选项用于在复选框单选按钮设置为真的情况下禁用复选框单选按钮，在使用 jQuery UI 设置为假的情况下启用复选框单选按钮。

**语法:**

```html
$( ".selector" ).checkboxradio({
  disabled: true
});
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> < link href = " https://Ajax . Google APIs . com/Ajax/libs/jqueryui/1 . 12 . 1/themes/cupertino/
> 
> " jquery-ui.css" rel="stylesheet " >

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel='stylesheet' href=
'https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/themes/cupertino/jquery-ui.css'>

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
                  disabled: true
              });
            }); 
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/ce66bce5e908733926bd3e12fbb089a7.png)