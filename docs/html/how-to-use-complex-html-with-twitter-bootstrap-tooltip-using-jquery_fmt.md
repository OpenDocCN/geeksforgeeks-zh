# 如何使用 jQuery 配合 Twitter Bootstrap 工具提示实现复杂 HTML

> 原文：[https://www.geeksforgeeks.org/how-to-use-complex-html-with-twitter-bootstrap-tooltip-using-jquery/](https://www.geeksforgeeks.org/how-to-use-complex-html-with-twitter-bootstrap-tooltip-using-jquery/)

**Bootstrap 工具提示**以图形方式为我们提供关于特定元素的**提示**。工具提示用于性能原因，因此可以根据需求领域进行定制。Tooltip 是使用 JavaScript 实现的，它依赖于第三方库 `popper.js` 来定位。

它基于使用光标指针悬停的概念，当指针悬停在元素上时，可能会按照代码中的指示在任何 4 个方向（左、右、上、下）弹出/出现提示。

**一些一般的例子：**

*   在登录页面中，**密码**工具提示会弹出要求，如长度应为 8 个字符，以大写字母开头等。
*   对于**名字**，可能会弹出只需键入名字，不需要键入中间名或姓。

JavaScript 片段：

```javascript
// Write Javascript code here
$(function () {
  $('[data-toggle="tooltip"]').tooltip()
})
```

**注意：** 使用 HTML、CSS、Bootstrap、JavaScript 和 jQuery。

## 方法 1：四个方向的工具提示按钮

下面的实现为四个按钮（左、右、上、下）及其各自的工具提示完成，当光标悬停在按钮上时，这些工具提示分别指示按钮的位置。

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content="width=device-width,initial-scale=1.0" />
    <title>HTML with twitter Bootstrap tooltip using jQuery</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVqOtnepnHVP9aJ7xS" crossorigin="anonymous"></script>
    <script type="text/javascript">
        $(document).ready(function() {
            $("#toptip").tooltip({
                placement: "top"
            });
            $("#bottomtip").tooltip({
                placement: "bottom"
            });
            $("#lefttip").tooltip({
                placement: "left"
            });
            $("#righttip").tooltip({
                placement: "right"
            });
        });
    </script>
</head>

<body>
    <center>
        <div class="container">
            <h1><u>Bootstrap Tooltip Demo</u></h1>
            <br/><br/>
            <div>
                <button type="button" id="toptip" class="btn btn-danger" title="A Tooltip with Top placement">Top Tooltip demo</button>
                <br><br>
                <button type="button" id="bottomtip" class="btn btn-info" title="A Tooltip with Bottom placement">Bottom Tooltip demo</button>
                <br><br>
                <button type="button" id="lefttip" class="btn btn-success" title="A Tooltip with Left placement">Left Tooltip demo</button>
                <br><br>
                <button type="button" id="righttip" class="btn btn-warning" title="A Tooltip with Right placement">Right Tooltip demo</button>
            </div>
        </div>
    </center>
</body>

</html>
```

**输出：**
![](img/fff51da9d6d4d3968a4a003667b849b3.png)

## 方法 2：带工具提示的注册页面

下面的实现是一个带有工具提示的注册页面，用于提供建议/推荐。HTML 中的 `form` 标签用于创建表单，并相应地添加工具提示属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Bootstrap Grid</title>
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
    <!-- Optional theme -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.2/css/bootstrap-theme.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
    <!-- Latest compiled and minified JavaScript -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.2/js/bootstrap.min.js"></script>
    <script type="text/javascript">
        $(document).ready(function() {
            $('#name').tooltip({
                'trigger': 'focus',
                'title': 'Name is Required'
            });
            $('#email').tooltip({
                'trigger': 'focus',
                'title': 'Email is Required'
            });
            $('#password').tooltip({
                'trigger': 'focus',
                'title': "Password is Required"
            });
        });
    </script>
    <style>
        .serif {
            font-family: "Times New Roman", Times, serif;
        }
        p {
            padding: 20px;
        }
    </style>
</head>

<body>
    <h1><p class="serif">Sign Up Sample Page</p></h1>
    <div class="container" style="padding:50px;">
        <form role="form">
            <div class="form-group">
                <label for="firstname">Name</label>
                <input type="text" name="Name" class="form-control" id="name" placeholder="Enter Name">
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="text" name="email" class="form-control" id="email" placeholder="Enter email">
            </div>
            <div class="form-group">
                <label for="Password">Password</label>
                <input type="password" name="password" class="form-control" id="password" placeholder="Enter Password">
            </div>
        </form>
    </div>
</body>

</html>
```

**输出：**
![](img/c8d6c69b8b155f65aa0f4d8c9c4802bc.png)