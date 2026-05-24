# 如何使用 jQuery Mobile 创建隐藏在输入区的标签？

> 原文:[https://www . geesforgeks . org/如何创建标签-隐藏在输入区域-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-label-hidden-in-input-area-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。

在本文中，我们将使用 jQuery Mobile 创建一个隐藏的标签。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个隐藏的标签。我们使用 class="ui-hidden-accessible "属性来隐藏文本标签。

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
            Design a Label hidden 
            using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="TextInput1" class="ui-hidden-accessible">
                Input Text:
            </label>
            <input type="text" data-clear-btn="false" 
                name="TextInput1" id="TextInput1" value="">

            <label for="TextInput2" class="ui-hidden-accessible">
                Text Input with clear Button:
            </label>
            <input type="text" data-clear-btn="true" 
                name="TextInput2" id="TextInput2" value="">

            <label for="searchInput1" class="ui-hidden-accessible">
                Search Input:
            </label>
            <input type="search" name="searchInput1" 
                id="searchInput1" value="">

            <label for="textareaInput" class="ui-hidden-accessible">
                Search Input with clear Button:
            </label>
            <textarea cols="40" rows="8" name="textareaInput" 
                id="textareaInput" value=""></textarea>
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/5197273bfabe7ee42780833b60de1752.png)