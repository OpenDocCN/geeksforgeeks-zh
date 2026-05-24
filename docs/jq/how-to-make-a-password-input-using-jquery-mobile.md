# 如何使用 jQuery Mobile 进行密码输入？

> 原文:[https://www . geesforgeks . org/如何制作密码-输入-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-password-input-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个密码输入。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个密码输入区。我们使用 type="password "属性来设置密码。

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
            Design a Password Input using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="password-1">
                Password Input Area:
            </label>
            <input type="password" data-clear-btn="false"
                name="password-1" id="password-1" 
                value="" autocomplete="off">

            <label for="password-2">
                Password Input Area with clear Button:
            </label>
            <input type="password" data-clear-btn="true"
                name="password-2" id="password-2" 
                value="" autocomplete="off">
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/b7b1e13588d84dffa90a5fd08bd6097a.png)