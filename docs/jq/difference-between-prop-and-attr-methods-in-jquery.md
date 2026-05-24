# jQuery 中 prop()和 attr()方法的区别

> 原文:[https://www . geesforgeks . org/prop-and-attr-methods-in-jquery/](https://www.geeksforgeeks.org/difference-between-prop-and-attr-methods-in-jquery/)

在本文中，我们将了解 JQuery 中 prop()和 attr()之间的区别。jQuery 是最快的轻量级 JavaScript 库，用于简化 HTML/CSS 文档(更准确地说是文档对象模型(DOM))和 JavaScript 之间的交互。JQuery 因其座右铭**“少写多做”而广为人知**简单来说就是只要写几行代码就可以达到目的。

**jQuery。prop()方法:**此方法用于获取匹配元素集中第一个元素的属性值。

**语法:**

```html
$(selector).prop(property)
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("button").click(function () {
                var $val = $("div");
                $val.prop("font-size", "5px");
                $val.append("Property value = "
                    + $val.prop("font-size"));
            });
        });
    </script>

    <style>
        body {
            text-align: center;
        }

        button {
            background-color: #4CAF50;
            /* Green */
            border: none;
            color: white;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
        }
    </style>
</head>

<body>
    <h1 style="color:green">
        GeeksForGeeks
    </h1>

    <button>Property</button>
    <br>
    <div></div>
</body>

</html>
```

**输出:**

![](img/c6b716a84e3db5726d3bd1211c11db8f.png)

**jQuery。attr()方法:**该方法用于从匹配集中的第一个元素获取属性值，或者将属性值设置到所有匹配的元素上。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>The jQuery Example</title>

    <script type="text/javascript" src=
"https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js">
    </script>

    <script type="text/javascript">
        $(document).ready(function () {
            var title = $("h1").attr("title");
            $("#divid").text(title);
        });
    </script>

    <style>
        body {
            text-align: center;
        }
    </style>
</head>

<body>
    <div>
        <h1 style="color:green"
            title="A computer science protal for Geeks">
            GeeksForGeeks
        </h1>
        <p id="myid">GeeksForGeeks</p>

        <div id="divid"></div>
    </div>
</body>

</html>
```

**输出:**

![](img/5b6d04f31d47ef8d5b56a0007f32f996.png)

**解释:**在上面的例子中，你可以注意到‘极客的计算机科学门户’是极客的一个价值。

**之间的区别。prop()和 attr()方法分别是:**

<figure class="table">

| 

prop()方法

 | 

attr()方法

 |
| --- | --- |
| This method returns the current value. | This method returns the default value. |
| This method is mainly used when users want to change the value of HTML tag attributes. | This method is mainly used to set the default value of HTML tag attributes. |
| It changes the attributes of the HTML tag according to the DOM tree. | It changes the attributes of the HTML tag. |

</figure>