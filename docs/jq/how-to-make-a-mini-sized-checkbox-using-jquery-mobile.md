# 如何使用 jQuery Mobile 制作迷你大小的复选框？

> 原文:[https://www . geeksforgeeks . org/how-to-make-mini-size-checkbox-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-mini-sized-checkbox-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个迷你大小的复选框。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

**示例:**我们将使用 jQuery Mobile 创建一个迷你大小的复选框。我们使用 input type="checkbox "属性创建复选框按钮，并使用 data-mini="true "属性创建一个小尺寸的复选框。

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
            Design a Mini sized Checkbox
            using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <input type="checkbox" name="minicheckbox"
                id="minicheckbox" data-mini="true">
            <label for="minicheckbox">Check Here</label>
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/59cab9b92545991de6c34a1ae74ff6b3.png)