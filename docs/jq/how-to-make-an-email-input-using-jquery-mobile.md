# 如何使用 jQuery Mobile 进行电子邮件输入？

> 原文:[https://www . geeksforgeeks . org/如何制作电子邮件-输入-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-an-email-input-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑、an 和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个电子邮件输入。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个电子邮件输入区域。我们使用 type="email "属性来设置电子邮件。

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
            Design an Email Input using jQuery Mobile
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
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/82732eb5958d73140b283103a051e08d.png)