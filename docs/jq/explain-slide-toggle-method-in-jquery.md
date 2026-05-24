# 解释 jQuery

中的滑动切换方法

> 原文:[https://www . geesforgeks . org/explain-slide-toggle-method-in-jquery/](https://www.geeksforgeeks.org/explain-slide-toggle-method-in-jquery/)

[**slide toggle()**](https://www.geeksforgeeks.org/jquery-slidetoggle-method/)**是 jQuery 中的一个方法，它是两个独立方法的替代方法，即[**【slide up()**](https://www.geeksforgeeks.org/jquery-slideup-with-examples/)和[**【slide down()**](https://www.geeksforgeeks.org/jquery-slidedown-method/)。**

**这实际上是在使用元素的 CSS [*显示*](https://www.geeksforgeeks.org/css-display-property/) 属性，并为其提供一个轻微的动画。如果元素有“*显示:无*”，则**向下滑动()**功能被切换，如果显示被设置为任何其他属性，**向上滑动()**进入图片。**

****语法:****

```html
$(<selector>).slideToggle(<speed>,<ease_property>,<function>);
```

****参数:**可以将多个参数传递给函数，如动画的速度、缓和属性的类型(摇摆&线性)和回调函数。**

*   ****速度:**速度参数默认值为 400 毫秒。这是一个可选参数。其他选项有“快”和“慢”。**
*   ****ease _ property:****默认属性为“摇摆”和“线性”。这也是一个可选参数。****
*   ******callback_function:** 这个必须由用户定义，也是可选参数。****

******示例 1:** 以下示例演示了 **slideToggle()** 方法。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html>

<head>
    <title>slideToggle functionality</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>
</head>

<body>
    <h2>Welcome To GFG</h2>

    <button id="slide-toggle">toggle</button>

    <h1 id="textbox">geeksforgeeks.org</h1>

    <script>
        $("#slide-toggle").on("click", function () {
            $("#textbox").slideToggle();
        });
    </script>
</body>

</html>**
```

******输出:******

****![](img/04ef9ca4f5037afff32279dbcec92574.png)****

******示例 2:** 以下示例代码演示了 **slideToggle()** 方法中参数的用法。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html>

<head>
    <title>slideToggle functionality</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>
</head>

<body>
    <h2>Welcome To GFG</h2>

    <button id="slide-toggle">toggle</button>

    <h1 id="textbox">geeksforgeeks.org</h1>

    <script>
        $("#slide-toggle").on("click", function () {
            $("#textbox").slideToggle(3000, "swing", function () {
                alert("slide toggle clicked");
            });
        });
    </script>
</body>

</html>**
```

******输出:******

****![](img/11978b9516b31f9f10a311715d22c654.png)****

****这就是 **slideToggle()** 功能的工作原理，这些通常对正常工作的网站有用。如果我们想创造一种美感，这个功能不是很有用，因为动画不是很流畅。****