# JQuery delivered . pipe()方法

> 原文:[https://www.geeksforgeeks.org/jquery-deferred-pipe-method/](https://www.geeksforgeeks.org/jquery-deferred-pipe-method/)

jQuery 中的**delivered . pipe()**方法用于添加实用方法进行过滤，链式 delivers。

**语法:**

```html
deferred.pipe([doneFilter][, failFilter][, progressFilter])
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **doneFilter:** 是一个可选函数，在解决延迟问题时调用。
*   **故障过滤器:**这是一个可选功能，当延迟被拒绝时调用。
*   **进度过滤器:**这是一个可选函数，当进度通知被发送到延迟对象时调用。

**返回值:**该方法返回延迟对象。

**示例 1:** 在本例中，管道方法是用 resolve 方法调用的。

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

<p>
        JQuery | deferred.pipe() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG"></p>

    <script>
        function Geeks() {
            var def = $.Deferred(),
                filter = def.pipe(function (val) {
                    return "pipe() is called with "
                                + val;
                });

            def.resolve('resolve method');
            filter.done(function (val) {
                $('#GFG').append(val);
            });
        }
    </script>
</body>

</html>
```

**输出:**

![](img/518a4fdf9b77e69c53453b78c626afbd.png)

**示例 2:** 在本例中，管道方法是用 reject 方法调用的。

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

<p>
        JQuery | deferred.pipe() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG"></p>

    <script>
        function Geeks() {
            var def = $.Deferred(),
                filter = def.pipe(null,
                        function (val) {
                    return "pipe() is called with "
                            + val;
                });
            def.reject('reject method');
            filter.fail(function (val) {
                $('#GFG_DOWN').append(val);
            });
        }
    </script>
</body>

</html>
```

**输出:**

![](img/50a09bc73e07b8e3d62d2a24c9fd5e88.png)