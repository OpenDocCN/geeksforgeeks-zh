# 如何创建 jQuery UI 自动完成？

> 原文:[https://www . geesforgeks . org/how-create-jquery-ui-autocomplete/](https://www.geeksforgeeks.org/how-to-create-jquery-ui-autocomplete/)

在本文中，我们将看到如何使输入字段(输入文本)自动完成。为此，我们使用 jquery UI 库。在这里，我们采用输入字段，用户可以通过输入搜索词和过滤器，轻松地从预先填充的值列表中查找和选择。

**步骤:**

*   包括 jQuery UI 库的 CDN 路径，按照下面代码遵循的特定顺序，对于 CSS 和 JavaScript 都遵循这个步骤。
*   在包含 jQuery CDN 文件之后，您必须在正文标记的末尾或紧接在正文标记之前附加一个 [<脚本>标记](https://www.geeksforgeeks.org/html-script-tag/)。
*   然后遵循 jQuery UI 提供的自动完成 API 函数的模板。

**语法:**

```html
$(element).autocomplete(options);
```

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">
    <title>jQuery UI Autocomplete</title>
    <link rel="stylesheet" href=
"//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <link rel="stylesheet" 
        href="/resources/demos/style.css">
    <script src=
"https://code.jquery.com/jquery-1.12.4.js">
    </script>
    <script src=
"https://code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>
</head>

<body style="border:2px solid green;min-height:240px;">
    <div style="display:flex; justify-content:center">
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>
    </div>

    <div class="ui-widget" style="display:flex;
        justify-content:center;margin-top:20px;">
        <input id="langs" placeholder="Your Favorite language">
    </div>

    <script>
        $(function () {
            let availableTags = [
                "ActionScript",
                "AppleScript",
                "Asp",
                "BASIC",
                "C",
                "C++",
                "Clojure",
                "COBOL",
                "ColdFusion",
                "Erlang",
                "Fortran",
                "Groovy",
                "Haskell",
                "Java",
                "JavaScript",
                "Lisp",
                "Perl",
                "PHP",
                "Python",
                "Ruby",
                "Scala",
                "Scheme"
            ];
            $("#langs").autocomplete({
                source: availableTags
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/8f760ae09e1a68e45edfb0e7610c7b5c.png)

输出