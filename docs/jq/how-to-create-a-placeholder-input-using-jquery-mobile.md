# 如何使用 jQuery Mobile 创建占位符输入？

> 原文:[https://www . geeksforgeeks . org/如何创建占位符-输入-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-placeholder-input-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个占位符输入。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个占位符输入区域。我们使用 placeholder =“value”属性来设置 placeholder 的值。

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
            Design a Placeholder Input using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="EmailInput1">
                Email Input Area:
            </label>
            <input type="email" data-clear-btn="false" 
                name="EmailInput1" id="EmailInput1" 
                value="" placeholder="Enter Email...">

            <label for="EmailInput2">
                Email Input Area with clear Button
            </label>
            <input type="email" data-clear-btn="true" 
                name="EmailInput2" id="EmailInput2" 
                value="" placeholder="Enter Email...">

            <label for="password-1">
                Password Input Area:
            </label>
            <input type="password" data-clear-btn="false"
                name="password-1" id="password-1" 
                value="" placeholder="Enter Password...">

            <label for="password-2">
                Password Input Area with clear Button:
            </label>
            <input type="password" data-clear-btn="true"
                name="password-2" id="password-2" 
                value="" placeholder="Enter Password...">
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/ca1de2c247d957a09744446e8a2587dc.png)