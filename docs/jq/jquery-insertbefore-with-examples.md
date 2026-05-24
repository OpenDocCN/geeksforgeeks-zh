# jQuery | insertBefore()带示例

> 原文:[https://www . geeksforgeeks . org/jquery-insert before-with-examples/](https://www.geeksforgeeks.org/jquery-insertbefore-with-examples/)

**insertBefore()** 是 jQuery 中的一个内置方法，用于在指定的元素前插入一些 HTML 内容。HTML 内容将在指定元素的每次出现之前插入。
**语法:**

```html
$(content).insertBefore(target)

```

这里的内容是需要在指定目标之前插入的 HTML 内容。
**参数:**它接受一个参数“目标”，该参数是内容要插入的目标。
**返回类型:**不返回值。

<center>**jQuery code to show the working of insertBefore() method:**</center>

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
                // insertBefore
                $("<p>You should follow GeeksForGeeks</p>").insertBefore("p");
            });
        });
    </script>
</head>

<body>

    <p>To learn jQuery </p>

    <div>Click here to complete</div>

</body>

</html>
```

**输出:**
点击 div 内容前-

```html
To learn jQuery
Click here to complete

```

点击 div 内容后-

```html
You should follow GeeksForGeeks
To learn jQuery 
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
                // insertBefore
                $("<p>You should follow GeeksForGeeks</p>").insertBefore("p");
            });
        });
    </script>
</head>

<body>

    <p>To learn jQuery </p>

    <p> To learn coding </p>

    <div>Click here to complete</div>

</body>

</html>
```

**输出:**
点击 div 内容前-

```html
To learn jQuery 
To learn coding 
Click here to complete

```

点击 div 内容后-

```html
You should follow GeeksForGeeks
To learn jQuery 
You should follow GeeksForGeeks
To learn coding
Click here to complete

```