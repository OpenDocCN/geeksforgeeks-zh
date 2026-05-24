# jQuery Mobile vmousedown 事件

> 原文:[https://www . geesforgeks . org/jquery-mobile-vmousedown-event/](https://www.geeksforgeeks.org/jquery-mobile-vmousedown-event/)

**jQuery Mobile***vmousedown*事件在我们点击元素时被触发。我们可以将这个事件用于不同的目的。

**语法:**

```html
jQuery( ".selector" ).on( "vmousedown", function( event ) {  } )
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
        $(document).on('vmousedown', 'a', 
            function(event) {
            console.log(event)
        })
    </script>
</head>

<body>

    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Mousedown Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>

</body>

</html>
```

**输出:**

![](img/5c05996e51628683a17b9dbbff40efbe.png) ![](img/04704edd9ea9213c2e6c5573f769fd0f.png)

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
        $(document).on('vmousedown', 'a', function() {
            console.log('Mousedown event fired');
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Mousedown Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/974cfd2a399ba7bb3bb6f16270b4483c.png) ![](img/824f5e1b6fdd54b16e46c8379df7d3ee.png)