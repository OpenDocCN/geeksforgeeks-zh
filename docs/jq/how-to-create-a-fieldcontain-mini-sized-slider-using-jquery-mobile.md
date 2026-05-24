# 如何使用 jQuery Mobile 创建一个字段容器，小尺寸的滑块？

> 原文:[https://www . geeksforgeeks . org/how-create-a-field contain-mini-size-slider-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-fieldcontain-mini-sized-slider-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 **jQuery Mobile 创建一个字段容器，小尺寸的滑块。**

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**我们将使用 jQuery Mobile 创建一个 Fieldcontain，小型滑块。滑块是使用滑块插入数据的输入类型。我们使用*类型=“范围*”属性和<输入>元素来创建一个滑块。

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
            Design a Fieldcontain, mini sized 
            Slider using jQuery Mobile
        </h4>

        <form style="width: 50%;">
            <div class="ui-field-contain">
                <label for="slider">
                    Fieldcontain, mini sized Slider:
                </label>

                <input type="range" name="slider" 
                    id="slider" data-track-theme="b" 
                    data-mini="true" data-theme="b" 
                    min="0" max="100" value="50">
            </div>
        </form>
    </center>
</body>

</html>
```

**输出:**

![](img/d1d9b110a9fdb026d67e965aa8815aee.png)