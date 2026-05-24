# 如何使用 jQuery Mobile 创建日期时间输入？

> 原文:[https://www . geeksforgeeks . org/如何创建日期时间-输入-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-datetime-input-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 **jQuery Mobile** 创建一个日期时间输入区域。

**方法:**添加项目所需的 jQuery 移动脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个日期时间输入区域。我们使用 *type="datetime"* 属性来设置 *datetime* 。

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
            Design a Datetime Input using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <label for="datetimeInput1">Datetime Input Area:</label>
            <input type="datetime" data-clear-btn="false" 
                name="datetimeInput1" id="datetimeInput1" value="">

            <label for="datetimeInput2">
                Datetime Input Area with Clear Button:
            </label>
            <input type="datetime" data-clear-btn="true" 
                name="datetimeInput2" id="datetimeInput2" value="">

            <label for="datetimeInput3">
                Datetime-local Input Area:
            </label>
            <input type="datetime-local" data-clear-btn="false" 
                name="datetimeInput3" id="datetimeInput3" value="">

            <label for="datetimeInput14">
                Datetime-local Input Area with Clear Button:
            </label>
            <input type="datetime-local" data-clear-btn="true" 
                name="datetimeInput4" id="datetimeInput4" value="">
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/a034ca109e37c706dc51840abe04ed26.png)