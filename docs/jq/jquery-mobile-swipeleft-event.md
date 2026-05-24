# jQuery 手机 swipeleft 事件

> 原文:[https://www . geesforgeks . org/jquery-mobile-swipeleft-event/](https://www.geeksforgeeks.org/jquery-mobile-swipeleft-event/)

**jQuery Mobile***swipeleft*事件在元素区域向左滑动时触发。我们可以将这个事件用于不同的目的。

**语法:**

```html
jQuery( ".selector" ).on( "swipeleft", function( event ) {  } )
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
        $(document).on('swipeleft', 'a', function() {
            console.log('swipeleft event fired');
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>swipeleft Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/d0fa2264fc47cc39cfa451957ad318c5.png) ![](img/17e3f2c081318503f59d51e5b9961d20.png)

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
        $(document).on('swipeleft', 'a', function(event) {
            console.log(event)
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>swipeleft Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/31f3b4895b4163c0fb7d2e1134aa7d68.png) ![](img/f3f03219090efd48490f27bf24d3a3fb.png)