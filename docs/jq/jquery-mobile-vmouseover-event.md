# jQuery 手机 vmouseover 事件

> 原文:[https://www . geesforgeks . org/jquery-mobile-vmouseover-event/](https://www.geeksforgeeks.org/jquery-mobile-vmouseover-event/)

**jQuery Mobile** 当我们将鼠标悬停在一个元素上时，会触发 vmouseover 事件。我们可以将这个事件用于不同的目的。

**语法:**

```html
jQuery( ".selector" ).on( "vmouseover", function( event ) {  } )
```

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”/">
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
        $(document).on('vmouseover', 'a',
            function (event) {
                console.log(event);
            });
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>
            Mouseover Event using
            jQuery Mobile
        </h4>
    </center>
    <a data-role="button" 
        id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/96186d7f1e00521bfc51a796d6780336.png)

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
        $(document).on('vmouseover', 'a',
            function () {
                console.log('mouseover event');
            });
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>
            Mouseover Event using
            jQuery Mobile
        </h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/75f86cc8da3ca4bb72c6f14dd53d1d91.png)