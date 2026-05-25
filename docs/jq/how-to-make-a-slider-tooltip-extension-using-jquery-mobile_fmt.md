# 如何使用 jQuery Mobile 制作滑块工具提示扩展？

> 原文：[https://www.geeksforgeeks.org/how-to-make-a-slider-tooltip-extension-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-slider-tooltip-extension-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个滑块工具提示扩展。

## 方法

添加项目所需的 jQuery Mobile 脚本。

> ```html
> <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
> <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
> <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
> ```

## 示例

在本例中，我们将使用 jQuery Mobile 创建一个 Basic 滑块。滑块是一种使用滑块插入数据的输入类型。我们使用 `type="range"` 属性配合 `<input>` 元素来创建一个 Slider。也可以使用 `data-show-value="true"` 和 `data-popup-enabled="true"` 属性来添加工具提示。

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
            Design a Slider tooltip extension
            using jQuery Mobile
        </h4>

<form style="width: 50%;">
            <label for="slider">
                Slider Tooltip:
            </label>
            <input type="range" name="slider" 
                id="slider" min="0" max="100" 
                value="50" data-popup-enabled="true">

<label for="slider">
                Theme Slider Tooltip:
            </label>
            <input type="range" name="slider" 
                id="slider" data-track-theme="b" 
                data-theme="b" min="0" max="100"
                value="50" data-popup-enabled="true">

<label for="slider">
                Theme Slider Tooltip with
                Showing Value:
            </label>
            <input type="range" name="slider" 
                id="slider" data-track-theme="b" 
                data-theme="b" min="0" max="100"
                value="50" data-show-value="true" 
                data-popup-enabled="true">
        </form>
    </center>
</body>

</html>
```

**输出：**

![](img/c7647e5b1fc938e3f7e389204b64bf20.png)