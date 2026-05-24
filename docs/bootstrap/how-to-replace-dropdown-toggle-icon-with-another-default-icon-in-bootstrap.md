# 如何在 Bootstrap 中用另一个默认图标替换下拉切换图标？

> 原文:[https://www . geesforgeks . org/如何替换-下拉-切换-图标替换-另一个-默认-引导图标/](https://www.geeksforgeeks.org/how-to-replace-dropdown-toggle-icon-with-another-default-icon-in-bootstrap/)

Bootstrap 提供了向我们的网站添加下拉菜单的选项。下拉按钮上的默认图标是“向下实心箭头”标志。尽管它服务于它的目的，现在大多数现代网站使用 Bootstrap。因此，对于访问者来说，图标可能看起来非常普通。

**程序:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>Bootstrap dorpdown</title>
    <meta name="viewport" 
          content="width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>

    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>

    <style>
        .container{
            margin:20px;
        }
        h2{
            color:green;
        }
    </style>
</head>

<body>
    <div class="container">
        <h2>GeeksforGeeks</h2>
        <p>A Computer Science Portal for Geeks</p>
        <div class="dropdown">
            <button type="button" 
                    class="btn btn-success dropdown-toggle" 
                    data-toggle="dropdown">
                Dropdown
            </button>
            <div class="dropdown-menu">
                <a class="dropdown-item" href="#">Option A</a>
                <a class="dropdown-item" href="#">Option B</a>
                <a class="dropdown-item" href="#">Option C</a>
                <a class="dropdown-item" href="#">Option D</a>
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/a011095206586ae8c1e08f44b2692a27.png)

但是，可以将默认引导图标更改为您选择的图标。您也可以使该图标可移动，下面的步骤将继续解决方案。

*   **第一步:**去一个外部图标网站，比如 Font Awesome。将其 CDN 链接嵌入网页的<标题>标签中。

    > <link rel="”stylesheet”" href="”https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css”">

*   **第二步:**将**下拉菜单的 CSS 切换**到**显示:无**。这将使按钮上的实心下拉标志消失。不过，**’！重要提示:为了查看网页上的变化，还必须添加“**”。

    ```html
    .dropdown-toggle::after {
        display: none !important;
    }

    ```

*   **第三步:**应用完 CSS 后，从外部图标网站复制想要在网页上显示的图标的嵌入代码，粘贴到按钮标签里面。就像在这个例子中，我们使用了'加号'的图标。
*   **第四步:**新图标将开始在网页上显示。

**注意:**下面程序代码的下拉图标也可以通过在图标上添加一行带有一键点击功能的 jQuery 代码来打开。

**程序:**本示例更改引导下拉图标的默认图标。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Bootstrap dorpdown</title>
    <meta name="viewport" 
          content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <link rel="stylesheet" href=
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>
    <style>
        .container{
            margin:20px;
        }
        h2{
            color:green;
        }
        .dropdown-toggle::after {
            display: none !important;
        }
        .fa {
            margin:2px;
            color:white;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>GeeksforGeeks</h2>
        <p>A Computer Science Portal for Geeks</p>
        <div class="dropdown">

            <!-- Dropdown button -->
            <button type="button" 
                    class="btn btn-success dropdown-toggle" 

                    data-toggle="dropdown">
                Dropdown
                <a href="javascript:void(0);" 
                   class="icon" 
                   onclick="geeksforgeeks()">

                    <!-- Chnaging the default icon with toggle-->
                    <i onclick="myFunction(this)"
                       class="fa fa-plus-circle"></i>
                </a>
            </button>

            <!-- Dropdown options -->
            <div class="dropdown-menu">
                <a class="dropdown-item" href="#">Option A</a>
                <a class="dropdown-item" href="#">Option B</a>
                <a class="dropdown-item" href="#">Option C</a>
                <a class="dropdown-item" href="#">Option D</a>
            </div>
        </div>
    </div>
    <script> 

        // Function to toggle the plus menu into minus 
        function myFunction(x) { 
            x.classList.toggle("fa-minus-circle"); 
        } 
    </script> 
</body>

</html>
```

**输出:**
![](img/fce818c0c6277d1efad740c858682ac2.png)