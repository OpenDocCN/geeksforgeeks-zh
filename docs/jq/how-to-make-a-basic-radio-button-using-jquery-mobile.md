# 如何使用 jQuery Mobile 制作基本单选按钮？

> 原文:[https://www . geeksforgeeks . org/how-make-a-basic-radio-button-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-basic-radio-button-using-jquery-mobile/)

jQuery Mobile 是一项基于 we 的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。

在本文中，我们将使用 jQuery Mobile 创建一个基本单选按钮。

**进场:**

*   添加项目所需的 jQuery 移动脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

**示例:**我们将使用 jQuery Mobile 创建一个基本单选按钮。我们使用 input type="radio "属性创建单选按钮。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src="http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <h4>
            Design a Basic Radio Button
            using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="radioButton">Geeks</label>
            <input type="radio" name="radioButton" 
                id="radioButton" class="custom">

            <label for="radioButton1">GFG</label>
            <input type="radio" name="radioButton" 
                id="radioButton1" class="custom">

            <label for="radioButton2">GeeksforGeeks</label>
            <input type="radio" name="radioButton" 
                id="radioButton2" class="custom">

            <label for="radioButton3">Geeks Geeks</label>
            <input type="radio" name="radioButton"
                id="radioButton3" class="custom">
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/3f09c91aa6111984344abb63de3ae3bb.png)