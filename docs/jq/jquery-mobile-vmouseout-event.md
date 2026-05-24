# jQuery 手机 vmouseout 事件

> 原文:[https://www . geesforgeks . org/jquery-mobile-vmouseout-event/](https://www.geeksforgeeks.org/jquery-mobile-vmouseout-event/)

**jQuery Mobile***vmouseout*事件在我们悬停并将鼠标移出元素区域时触发。我们可以把这个事件用于不同的目的。

**语法:**

```html
jQuery( ".selector" ).on( "vmouseout", function( event ) {  } )
```

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”<br/">href = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . CSS "/>t1<src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></script>

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
        $(document).on('vmouseout', 'a', function(event) {
            console.log(event)
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Mouseout Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/82837512d58b4501f53c79a2e994fd6a.png) ![](img/e7b9881980102e1cbe4bd9fe6561e282.png)

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
        $(document).on('vmouseout', 'a', function() {
            console.log('Mouseout event fired');
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Mouseout Event using jQuery Mobile</h4>
    </center>

    <a data-role="button" id="gfg">click</a>
</body>

</html>
```

**输出:**

![](img/bd7cf46d7fa76dff76e1c8d6d084311a.png) ![](img/2f061cd71369b98ce295858c86e5c9c0.png)