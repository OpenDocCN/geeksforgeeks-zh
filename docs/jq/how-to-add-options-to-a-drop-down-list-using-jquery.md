# 如何使用 jQuery 给下拉列表添加选项？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-add-options-to-a-drop-down-list-using-jquery/) 将选项添加到下拉列表中

给定一个带有下拉列表菜单的 HTML 文档，我们的任务是使用 jQuery 向下拉列表添加更多选项。

**方法:**使用**追加()**方法向现有下拉列表添加更多选项:

```html
 var options = {
                val1: 'C#',
                val2: 'PHP'
            };
            var selectOption = $('#programmingLanguage');
            $.each(options, function (val, text) {
                selectOption.append(
                    $('<option></option>').val(val).html(text)
                );
            });
```

这是一个可用于向现有列表添加选项的小代码片段，该代码片段取自下面的演示，其中 **val1** 和 **val2** 具有**选项名称**， **programmingLanguage** 是用于**选择选项**的 **id** ，然后通过使用 **append()** 方法将新选项**与现有选项列表合并**。

JQuery 中 append()方法的详细说明可以在[这里](https://www.geeksforgeeks.org/jquery-append-method/)找到。

下面是演示上述方法的代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://code.jquery.com/jquery-3.3.1.min.js">
    </script>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Add an option to the dropdown list using jquery.</title>
</head>

<body>
    <h1 style="color: green;">GeeksForGeeks</h1>

<p>Programming Languages :</p>

    <select id='programmingLanguage'>
        <option value="Java" style="color: green; 
                font-weight: 700;">Java</option>
        <option value="Python" style="color: green; 
                font-weight: 700;">Python</option>
        <option value="CPP" style="color: green; 
                font-weight: 700;">CPP</option>
        <option value="C" style="color: green; 
                font-weight: 700;">C</option>
    </select>

<p> Click to add C# and PHP programming languages</p>

    <button onclick="addOption()">Add option</button>
    <!--Code to add an option to an existing set of option using jquery-->
    <script>
        function addOption() {
            var options = {
                val1: 'C#',
                val2: 'PHP'
            };
            var selectOption = $('#programmingLanguage');
            $.each(options, function (val, text) {
                selectOption.append(
                    $('<option></option>').val(val).html(text)
                );
            });
        }
    </script>
</body>

</html>
```

**输出:**

![](img/38381a4165ce8eae00381d5d23a4b60e.png)