# 如何在 jQuery 中从下拉列表中获取选择的选项？

> 原文:[https://www . geeksforgeeks . org/如何从 jquery 下拉列表中选择选项/](https://www.geeksforgeeks.org/how-to-get-selected-option-from-dropdown-in-jquery/)

在本文中，我们将学习如何从下拉列表中选择选项。本文需要对 HTML、CSS、JavaScript 和 jQuery 有一定的了解。我们可以通过使用 jQuery [val()方法](https://www.geeksforgeeks.org/jquery-val-with-examples/)来解决这个挑战。

jQuery 中的 **val()方法**用于设置或返回所选元素的属性值。此方法适用于 HTML 表单元素。

**语法:**

```html
$(selector).val()   // or
$(selector).val(value)  // or
$(selector).val(function(index, current_value))
```

此方法返回由 val()方法进行了指定更改的选定元素。

**示例:**

## 超文本标记语言

```html
<html>

<head>
    <title>
        How to get selected option from 
        Dropdown list using jQuery?
    </title>

    <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" 
        rel="stylesheet" integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
        crossorigin="anonymous">

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js">
    </script>
</head>

<body style="border: 2px solid green; min-height: 240px;">
    <div style="display: flex; justify-content: center;">
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>
    </div>

    <select class="form-select mx-auto" 
        aria-label="Default select example" 
        style="width: 200px; margin-top: 20px;"
        id="lang">

        <option selected>Select Language</option>
        <option>C</option>
        <option>Java</option>
        <option>Python</option>
    </select>

    <div id="show" style="display: flex;
        justify-content: center; margin-top: 20px;">
    </div>
</body>

<script>
    $('#lang').on('input', function () {
        $('#show').text($('#lang').val());
    })
</script>

</html>
```

**输出:**

![](img/0d4ef735a70cd4d724ffa01f19614437.png)

输出

**它是如何工作的？**

每当您从下拉列表中选择一个项目时，它将同时显示在下拉列表的下方。