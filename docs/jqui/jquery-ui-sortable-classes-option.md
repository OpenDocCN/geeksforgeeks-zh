# jQuery 用户界面可排序类选项

> 原文:[https://www . geesforgeks . org/jquery-ui-sortable-class-option/](https://www.geeksforgeeks.org/jquery-ui-sortable-classes-option/)

jQuery UI 可排序小部件类选项用于指定需要添加到小部件元素中的附加类。我们可以使用主题化部分中指定的任何类，这些类可以覆盖它们的值。

**语法:**

```html
 $( ".selector" ).sortable({
  classes: {
    "ui-sortable": "highlight"
  }
});
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css”">

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1">

    <link rel="stylesheet"
          href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">   
    <script 
          src="https://code.jquery.com/jquery-1.12.4.js">
    </script>
    <script 
           src="https://code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>
    <style>
        #sortable {
            list-style-type: none;
            width: 50%;
        }

        #sortable li {
            margin: 10px 0;
            padding: 0.5em;
            font-size: 25px;
            height: 20px;
        }
    </style>

    <script>
        $(function () {
            $("#sortable").sortable({
                classes: {
                    "ui-sortable": "highlight"
                }
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">GeeksforGeeks</h1>

        <h4>jQuery UI Sortable Widget classes Option</h4>

        <ul id="sortable">
            <li class="ui-state-default">BCD</li>
            <li class="ui-state-default">CAB</li>
            <li class="ui-state-default">BAC</li>
            <li class="ui-state-default">BCA</li>
            <li class="ui-state-default">ABC</li>
        </ul>
    </center>
</body>

</html>
```

**输出:**

![](img/74bd0f289446804656c1ddfc7de01309.png)