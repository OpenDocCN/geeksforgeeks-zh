# jQuery Deferred() 方法

> 原文: [https://www.geeksforgeeks.org/jquery-deferred-method/](https://www.geeksforgeeks.org/jquery-deferred-method/)

`jQuery.Deferred()` 方法是一个返回带有方法的实用程序对象的函数，这些方法可以向队列注册多个回调。它调用回调队列，并传递任何同步或异步函数的成功或失败状态。

**语法:**

```html
jQuery.Deferred([beforeStart])
```

**参数:**

*   `beforeStart`：这是一个函数，就在构造函数返回之前调用。

**返回值**: 这个方法创建并返回一个新的延迟对象。

下面讨论两个例子:

*   **示例**: 在此示例中，`Deferred()` 用于创建一个新对象，之后使用 `notify` 和 `resolve` 方法调用 `then()` 方法。

```html
<!DOCTYPE HTML>
<html>
<head>
    <title>
      jQuery.Deferred() method
    </title>
    <script src="https://code.jquery.com/jquery-3.5.0.js"></script>
</head>
<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>
    <p id="GFG_UP">
    </p>
    <button onclick = "Geeks();">
    click here
    </button>
    <p id="GFG_DOWN">
    </p>
    <script>
        var el_up = document.getElementById("GFG_UP");
        el_up.innerHTML = "jQuery.Deferred() method";
        function Func1(val, div){
          $(div).append("From doneCallbacks - " + val);
        }
        function Func2(val, div){
          $(div).append("From failCallbacks - " + val);
        }
        function Func3(val, div){
          $(div).append("From progressCallbacks - " + val);
        }
        function Geeks() {
            var def = $.Deferred();
            def.then(Func1, Func2, Func3);
            def.notify('Deferred "def" is notified.<br/>', '#GFG_DOWN');
            def.resolve('Deferred "def" is resolved.<br/>', '#GFG_DOWN');
        }
    </script>
</body>
</html>
```

**输出**:
![](img/7465d04cbf41e4ba5aeb54ff90448f4c.png)

*   **示例**: 在此示例中，使用了 `Deferred()` 方法，并检查了延迟对象的状态。

```html
<!DOCTYPE HTML>
<html>
<head>
    <title>
      jQuery.Deferred() method
    </title>
    <script src="https://code.jquery.com/jquery-3.5.0.js"></script>
</head>
<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>
    <p id="GFG_UP">
    </p>
    <button onclick = "Geeks();">
    click here
    </button>
    <p id="GFG_DOWN">
    </p>
    <script>
        var el_up = document.getElementById("GFG_UP");
        el_up.innerHTML = "jQuery.Deferred() method";
        var def = $.Deferred();
        def.resolve();
        function Geeks() {
            $('#GFG_DOWN').text('deferred state is ' + def.state());
        }
    </script>
</body>
</html>
```

**输出:**
![](img/902e37f7680a7385c6173641f005a189.png)