# jQuery | insertAfter()带示例

> 原文:[https://www . geeksforgeeks . org/jquery-insert after-with-examples/](https://www.geeksforgeeks.org/jquery-insertafter-with-examples/)

**insertAfter()** 是 jQuery 中的一个内置方法，用于在指定的元素后插入一些 HTML 内容。HTML 内容将在指定元素的每次出现后插入。
**语法:**

```html
$(content).insertAfter(target)

```

这里的“内容”是要插入到指定目标之后的 HTML 内容。
**参数:**取一个参数“target”，这个参数就是要插入内容的目标。
**返回值:**不返回值。

<center>**jQuery code to show the working of insertAfter() method:**</center>

**Code #1:**

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("div").click(function() {
                // insertAfter
                $("<p>You should follow GeeksForGeeks</p>").insertAfter("p");
            });
        });
    </script>
</head>

<body>

    <p>To learn jQuery : </p>

    <div>Click here to complete</div>

</body>

</html>
```

**输出:**
点击 div 内容前-

```html
To learn jQuery :
Click here to complete

```

**点击 div 内容后-**

```html
To learn jQuery :
You should follow GeeksForGeeks
Click here to complete

```

**代码#2:**

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("div").click(function() {
                // insertAfter
                $("<p>You should follow GeeksForGeeks</p>").insertAfter("p");
            });
        });
    </script>
</head>

<body>

    <p>To learn jQuery : </p>

    <p> To learn coding : </p>

    <div>Click here to complete</div>

</body>

</html>
```

**输出:**
点击 div 内容前-

```html
To learn jQuery :
To learn coding :
Click here to complete

```

点击 div 内容后-

```html
To learn jQuery :
You should follow GeeksForGeeks
To learn coding :
You should follow GeeksForGeeks
Click here to complete

```

jQuery 是一个开源的 JavaScript 库，它简化了 HTML/CSS 文档之间的交互，它以其“少写多做”的理念而闻名。
跟随本 [jQuery 教程](https://www.geeksforgeeks.org/jquery-tutorials/)和 [jQuery 示例](https://www.geeksforgeeks.org/jquery-examples/)可以从头开始学习 jQuery。