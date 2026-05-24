# jquery mobile vmouemove event

> 原文:[https://www . geesforgeks . org/jquery-mobile-vmousemove-event/](https://www.geeksforgeeks.org/jquery-mobile-vmousemove-event/)

**jQuery Mobile** 当我们在元素区域移动鼠标时，会触发 vmousemove 事件。我们可以将这个事件用于不同的目的。

**语法:**

```html
jQuery(".selector" ).on( "vmousemove", function( event ) {  })
```

**方法:**首先，添加项目所需的 jQuery 移动脚本。

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
        $(document).on('vmousemove', 'a',
        function(event) {
            console.log(event)
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Mousemove Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/7b73097890e406688906ebd1437823db.png) ![](img/b1b1d8d1844c4e1bcc2ee05fff518d9b.png)

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
        $(document).on('vmousemove', 'a', function() {
            $("#resultID").html(" Mousemove event fired");
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Mousemove Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
    <div id="resultID"></div>
</body>

</html>
```

**输出:**

![](img/8345ab878e60ec1135e1c808fbf2f760.png)