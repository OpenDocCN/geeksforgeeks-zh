# 如何使用 jQuery Mobile 创建文件输入？

> 原文:[https://www . geesforgeks . org/如何创建文件-输入-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-file-input-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个文件输入区。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个文件输入区。我们使用 type="file "属性来设置文件。

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
            Design a File Input using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="fileInput1">
                File Input Area:
            </label>
            <input type="file" data-clear-btn="false"
                name="fileInput1" id="fileInput1" value="">

            <label for="fileInput2">
                File Input Area with clear Button:
            </label>
            <input type="file" data-clear-btn="true"
                name="fileInput2" id="fileInput2" value="">
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/3bdc2220112e7b1cf680bfe6cf0f7dc7.png)