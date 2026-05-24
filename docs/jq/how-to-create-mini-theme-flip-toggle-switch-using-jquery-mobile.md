# 如何使用 jQuery Mobile 创建迷你主题翻转切换开关？

> 原文:[https://www . geesforgeks . org/how-create-mini-theme-flip-toggle-switch-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-mini-theme-flip-toggle-switch-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作迷你主题翻转开关。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
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
            Mini Theme Flip toggle switch 
            using jQuery Mobile
        </h4>
    </center>

    <form>
        <label for="geeks-1">Flip toggle switch</label>

        <select name="geeks-1" id="geeks-1" 
            data-role="slider" data-track-theme="a" 
            data-theme="b" data-mini="true">

            <option value="off">Off</option>
            <option value="on">On</option>
        </select>
    </form>
</body>

</html>
```

**输出:**

![](img/449c274c3f7f8b04cf20111158082757.png)