# 如何使用 jQuery Mobile 制作表单元素 Rangeslider？

> 原文:[https://www . geesforgeks . org/how-make-form-element-range slider-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-form-element-rangeslider-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作表单元素 Rangeslider。

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
            Form element Range slider 
            using jQuery Mobile
        </h4>
    </center>

    <form>
        <div data-role="rangeslider">
            <label for="Geeks1">Rangeslider:</label>
            <input type="range" name="gfg" 
                id="Geeks1" min="0" max="100" 
                value="30">

            <label for="Geeks2">Rangeslider:</label>
            <input type="range" name="gfg" 
                id="Geeks2" min="0" max="100" 
                value="70">
        </div>
    </form>
</body>

</html>
```

**输出:**

![](img/af98b3c477140dfe948dd45f70a51a28.png)