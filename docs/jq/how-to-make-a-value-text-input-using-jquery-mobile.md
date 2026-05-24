# 如何使用 jQuery Mobile 进行数值/文本输入？

> 原文:[https://www . geeksforgeeks . org/how-a-value-text-input-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-value-text-input-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个值/文本输入。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

**示例:**我们将使用 jQuery Mobile 创建一个值/文本输入区域。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src=
        "http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <h4>
            Design a Value/Text Input type
            using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="TextInput1">
                Input Text:
            </label>
            <input type="text" data-clear-btn="false"
                name="TextInput1" id="TextInput1"
                value="GeeksforGeeks">

            <label for="TextInput2">
                Text Input with clear Button:
            </label>
            <input type="text" data-clear-btn="true"
                name="TextInput2" id="TextInput2"
                value="GeeksforGeeks">

            <label for="searchInput1">
                Search Input:
            </label>
            <input type="search" name="searchInput1"
                id="searchInput1" value="GeeksforGeeks">

            <label for="textareaInput">
                Textarea Input with clear Button:
            </label>
            <textarea cols="40" rows="8" name="textareaInput"
                id="textareaInput">GeeksforGeeks
            </textarea>
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/b81313abd073db3eae5e798f790e548e.png)