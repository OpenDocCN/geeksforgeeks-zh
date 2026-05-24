# jQuery UI 输出附录选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-sortable-appendix-option/

当用鼠标拖动可排序元素时，可排序小部件*追加到*选项用于追加元素。

**语法:**

```html
$( ".selector" ).sortable({
  appendTo: document.body
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
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
        "//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <link rel="stylesheet" href="/resources/demos/style.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
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
                appendTo: document.body
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">GeeksforGeeks</h1>

        <h4>jQuery UI Sortable Widget appendTo Option</h4>

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

![](img/960cf46f0435a222db89451baef379bf.png)