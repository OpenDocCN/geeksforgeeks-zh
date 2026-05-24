# jQuery 手机页面初始化事件

> 原文:[https://www.geeksforgeeks.org/jquery-mobile-pageinit-event/](https://www.geeksforgeeks.org/jquery-mobile-pageinit-event/)

**jQuery Mobile** *页面初始化时触发*事件。我们可以把这个事件用于不同的目的**。**

**语法:**

```html
jQuery( ".selector" ).on( "pageinit", function( event ) {  } )
```

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**例 1:**

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

    <script type="text/javascript">
        $(document).on('pageinit', function() {
            console.log('pageinit event fired');
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>pageinit Event using jQuery Mobile</h4>
    </center>
</body>

</html>
```

**输出:**

![](img/f5fbe2b12f562c8f16d6adbbe7891f2f.png)

**例 2:**

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

    <script type="text/javascript">
        $(document).on('pageinit', function(event) {
            console.log(event)
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>pageinit Event using jQuery Mobile</h4>
    </center>
</body>

</html>
```

**输出:**

![](img/39741cbaf1e04c6e215e0e40d32110cd.png)