# 如何使用 jQuery Mobile 创建颜色输入？

> 原文:[https://www . geeksforgeeks . org/如何创建颜色-输入-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-color-input-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个颜色输入区域。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个颜色输入区域。我们使用 type="color "属性来设置输入区域的颜色。

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
            Design a Color Input using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="colorInput1">
                Color Input Area:
            </label>
            <input type="color" data-clear-btn="false" 
                name="colorInput1" id="colorInput1" value="">

            <label for="colorInput2">
                Color Input Area with clear Button:
            </label>
            <input type="color" data-clear-btn="true" 
                name="colorInput2" id="colorInput2" value="" >
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/5370798322b90500142e781cf9065e64.png)