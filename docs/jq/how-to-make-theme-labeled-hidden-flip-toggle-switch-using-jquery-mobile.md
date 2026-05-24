# 如何使用 jQuery Mobile 制作主题标签隐藏翻转开关？

> 原文:[https://www . geesforgeks . org/how-make-theme-tag-hidden-flip-toggle-switch-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-theme-labeled-hidden-flip-toggle-switch-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个主题标签隐藏翻转开关。

可以使用切换开关的“数据轨道主题”和“数据主题”属性来指定主题。可以在这些属性中指定的值是不同的可用色板，每个色板都有不同的外观。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”/">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**

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
            Theme Labeled hidden Flip toggle
            switch using jQuery Mobile
        </h4>
    </center>
    <form>
        <label for="geeks-1" 
            class="ui-hidden-accessible">
            Flip toggle switch
        </label>

        <select name="geeks-1" id="geeks-1" 
            data-role="slider" 
            data-track-theme="b" data-theme="a">

            <option value="off">Off</option>
            <option value="on">On</option>
        </select>
    </form>
</body>

</html>
```

**输出:**

![](img/22596203fb8f4774368b300345cd4165.png)