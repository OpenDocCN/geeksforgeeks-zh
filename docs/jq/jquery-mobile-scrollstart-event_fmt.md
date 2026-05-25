# jQuery Mobile scrollstart 事件

> 原文：[https://www.geeksforgeeks.org/jquery-mobile-scrollstart-event/](https://www.geeksforgeeks.org/jquery-mobile-scrollstart-event/)

`jQuery Mobile` 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。每当滚动开始时，`jQuery Mobile` 中的 `scrollstart` 事件就会被触发。我们可以将这个事件用于不同的目的。

**语法：**

```html
jQuery(".selector").on("scrollstart", function( event ) {  })
```

**方法：** 首先，添加项目所需的 `jQuery Mobile` 脚本。

```html
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
<script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
```

### 示例 1

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
        $(document).on('scrollstart', function() {
            console.log('scrollstart event fired');
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>
            scrollstart Event using jQuery Mobile
        </h4>
    </center>
    <div style="height: 800px;"></div>
</body>

</html>
```

**输出：**

![](img/b1bd13a0c02bac78968863f362fec054.png)

### 示例 2

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
        $(document).on('scrollstart', function(event) {
            console.log(event)
        })
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>
            scrollstart Event using jQuery Mobile
        </h4>
    </center>
    <div style="height: 800px;"></div>
</body>

</html>
```

**输出：**

![](img/9791f919f34aeb55b013a0afb7e7a12e.png)