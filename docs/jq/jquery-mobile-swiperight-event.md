# jQuery 移动 swiperight 事件

> 原文:[https://www . geesforgeks . org/jquery-mobile-swiperight-event/](https://www.geeksforgeeks.org/jquery-mobile-swiperight-event/)

**jQuery Mobile** 当我们在元素区域右扫时触发扫动事件。我们可以将这个事件用于不同的目的。

**语法:**

```html
jQuery( ".selector" ).on( "swiperight", function( event ) {  } )
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
        $(document).on('swiperight', 'a', function() {
            console.log('swiperight event fired');
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>swiperight Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/a356b573c543dd96fcde3d6beaf1ac94.png) ![](img/0de339373ad09e7392cbd226008463c7.png)

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
        $(document).on('swiperight', 'a', 
        function(event) {
            console.log(event)
        })
    </script>
</head>

<body>

    <center>
        <h1>GeeksforGeeks</h1>
        <h4>swiperight Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>

</body>

</html>
```

**输出:**

![](img/d3e0c3aacdff40335b9fe1882bd90950.png) ![](img/bb296ff0debd5b637b8786936ce990dc.png)