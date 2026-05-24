# 如何使用 jQuery Mobile 制作基本复选框标记？

> 原文:[https://www . geesforgeks . org/how-make-a-basic-checkbox-markup-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-basic-checkbox-markup-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个基本的 Checkbox 标记。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

**示例:**我们将使用 jQuery Mobile 创建一个基本复选框。我们使用 input type="checkbox "属性创建复选框。

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
            Design a Basic Checkbox markup
            using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label>
                <input type="checkbox" 
                    name="Checkbox ">Check Here
            </label>
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/1c0c6d983e424cb02d454708982c31cf.png)