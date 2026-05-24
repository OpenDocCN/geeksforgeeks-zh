# 如何使用 jQuery 给已经有类的元素添加新的类？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-add-a-new-class-to-an-element-that-already-has-a-class-using-jquery/) 将新类添加到已经有类的元素中

在本文中，我们将学习使用 jQuery 向已经有类的元素添加一个新类。要添加一个新类，我们使用 jQuery **addClass()** 方法。 **addClass()** 方法用于向每个选定的元素添加更多的类及其属性。它也可用于更改选定元素的属性。

**语法:**

```html
$(selector).addClass(className);
```

**参数:**接受一个参数“*类名*，即要添加的新类的名称。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <style>
        .GFG1 {
            color: green;
            font-weight: bold;
        }

        .GFG2 {
            font-size: 24px;
        }
    </style>

    <!-- Import jQuery cdn library -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("button").click(function () {
                $("p").addClass("GFG2");
            });
        });
    </script>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        How to add a new class to an element that
        <br>already has a class using jQuery?
    </h3>

    <p class="GFG1">
        GeeksforGeeks computer science portal
    </p>

    <button>Click Here!</button>
</body>

</html>
```

**输出:**

**点击按钮前:**

![](img/f10fa42c2c43d6c97cb34645c516e42d.png)

**点击按钮后:**

![](img/b0e8e31c8c9863ad8a9235c94693e257.png)