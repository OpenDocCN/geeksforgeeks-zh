# 如何使用 jQuery Mobile 创建时间输入？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-time-input-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-time-input-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个时间输入。

## 方法
添加项目所需的 jQuery Mobile 脚本。

> <link rel="stylesheet" href="`http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css`">
> <script src="`http://code.jquery.com/jquery-1.11.1.min.js`"></script>
> <script src="`http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js`"></script>

## 示例
我们将使用 jQuery Mobile 创建一个时间输入区域。我们使用 `type="time"` 属性在输入字段中设置时间。

### HTML
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
            Design a Time Input using jQuery Mobile
        </h4>

<form style="width: 50%;">
            <label for="timeInput1">Time Input Area:</label>
            <input type="time" data-clear-btn="false" 
                name="timeInput1" id="timeInput1" value="">

<label for="timeInput2">
                Time Input Area with clear button:
            </label>
            <input type="time" data-clear-btn="true" 
                name="timeInput2" id="timeInput1" value="">
        </form>
    </center>
</body>

</html>
```

## 输出
![](img/3b6e031ddd46a19d4bfd6d1b0227d72d.png)