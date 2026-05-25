# jQuery deferred.reject()方法

> 原文：[https://www.geeksforgeeks.org/jquery-deferred-reject-method/](https://www.geeksforgeeks.org/jquery-deferred-reject-method/)

jQuery 中的`deferred.reject()`方法用于拒绝一个 deferred 对象，并使用给定的参数调用任何 failCallbacks。

## 语法

```html
deferred.reject( [args] )
```

## 参数

*   `args`：这是一个传递给故障回调的可选参数。

## 返回值

该方法返回延迟对象。

## 示例 1：带参数调用

在本例中，使用参数调用`reject()`方法。

```html
<!DOCTYPE HTML>
<html>

<head>
    <script src="https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

    <p>
        jQuery | deferred.reject() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG"></p>

    <script>
        function Func(val, div) {
            $(div).append(val);
        }
        function Geeks() {
            var def = $.Deferred();
            def.fail(Func);
            def.progress(Func);
            def.reject('reject() method is '
                + 'called with arguments and'
                + ' Deferred object is '
                + 'rejected', '#GFG')
        } 
    </script>
</body>

</html>
```

**输出：**

![](/img/e59e21cd30ccf0bd19288c4c7d398bc5.png)

## 示例 2：不带参数调用

在本例中，调用`reject()`方法时没有参数。

```html
<!DOCTYPE HTML>
<html>

<head>
    <script src="https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

    <p>
        JQuery | deferred.reject() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG"></p>

    <script>
        function Func() {
            $('#GFG').append
                ("reject() method is called "
                + "without arguments and "
                + "Deferred object is rejected");
        }

        function Geeks() {
            var def = $.Deferred();
            def.fail(Func);
            def.progress(Func);
            def.reject()
        } 
    </script>
</body>

</html>
```

**输出：**

![](/img/ffcdeee9905ee980b6684c49e603542d.png)