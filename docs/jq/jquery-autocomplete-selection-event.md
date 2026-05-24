# jQuery |自动完成选择事件

> 原文:[https://www . geesforgeks . org/jquery-自动完成-选择-事件/](https://www.geeksforgeeks.org/jquery-autocomplete-selection-event/)

在网络世界中，使用自动完成 typeahead 输入是非常常见的做法。例如用户地址字段。为此，jQuery 中有一个非常常见的用户界面特性。
在搜索特定值的过程中， **jQuery UI 自动完成选择**功能为用户提供了一些输入区域的字符串建议，有效节省了时间。
当用户从预先填充的列表中选择一个选项时，自动完成选择操作被触发。
最常见的通用例子是被全球数百万用户使用的谷歌意见箱。该功能的最基本目的是用用户从列表中选择的值替换文本字段的值。它会触发多个事件，如聚焦、按键事件或用户输入的改变，这些事件用于调用不同的函数，返回描述聚焦或选定项目的对象。
该实现使用各种方式完成，例如从数据库表中获取数据来填充用户输入字段的值。它从相关数据库中选择以用户输入的关键字开始的字符串。与动态实现不同，您可以执行静态实现。例如，使用 XML 文件或列表是从变量数组中获取的。

**选择(事件，ui )** 只要从弹出列表中选择任何选项，该功能就会触发。它包含下面列出的两个参数:

*   **事件:**此参数提及用户触发的事件。
*   **ui:** 此参数提及包含所选项目的名称和值属性的对象。

**代码片段:**

```html
$( ".selector" ).autocomplete({
    select: function( event, ui ) {}
});

```

**例 1:**

```html
<!doctype html>
<html>

<head>
    <title>
        jQuery Autocomplete Selection Event
    </title>

    <link rel="stylesheet" href=
"//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">

    <script src="//code.jquery.com/jquery-1.12.4.js"></script>
    <script src="//code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>
</head>

<body>
    <label>Select Technology : </label>

    <input id="autocompleteInput">

    <script> 
        var tags = [ 
            "jQuery", "java", "php",
            "MySQL", "javascript", 
            "html", "C#", "C", "MongoDB" 
        ];

        $("#autocompleteInput").autocomplete({
            source: tags
        });
    </script>
</body>

</html>
```

**输出:**
![](img/49db930d47a34d68497d7cb24678eb6c.png)

**注:**在上例中，*源代码*实际定义了选择要使用的数据。

**例 2:**

```html
<!DOCTYPE html> 
<html> 

<head>
    <title>
        jQuery AutoComplete selection
    </title> 

    <link rel="stylesheet" href=
"http://code.jquery.com/ui/1.11.3/themes/ui-lightness/jquery-ui.css"/>

    <script src=
        "http://code.jquery.com/jquery-2.1.3.js">
    </script>

    <script src=
        "http://code.jquery.com/ui/1.11.2/jquery-ui.js">
    </script>

    <script>
        $(document).ready(function() {

             var tags = [
                 "Washington", "Cincinnati",
                 "Dubai", "Dublin", "Colombo",
                 "Culcutta"
            ];

            $('#input').autocomplete({
                source : tags,              
                select : showResult,
                focus : showResult,
                change :showResult
            })

            function showResult(event, ui) {
                $('#cityName').text(ui.item.label)
            }
        });
    </script>
</head>

<body>
    <form>     
        <div class="ui-widget">
            <label for="input">City Name : </label>
            <input id="input"/><br>

            Label of City Name: <div id="cityName"></div>            
        </div>
    </form>
</body>

</html>
```

**输出:**
![](img/7efffe129fdb1ed97326ea8dee480302.png)

**注意:**从以上两个代码示例中，可以观察到 *source* 参数占用了数组或函数回调结果等字符串选项列表。

jQuery 是一个开源的 JavaScript 库，它简化了 HTML/CSS 文档之间的交互，它以其“少写多做”的理念而闻名。
跟随本 [jQuery 教程](https://www.geeksforgeeks.org/jquery-tutorials/)和 [jQuery 示例](https://www.geeksforgeeks.org/jquery-examples/)可以从头开始学习 jQuery。