# jQuery 回调. lock()方法

> 原文:[https://www.geeksforgeeks.org/jquery-callbacks-lock-method/](https://www.geeksforgeeks.org/jquery-callbacks-lock-method/)

jQuery 中的**回调. lock()** 方法用于锁定状态中的回调列表。

**语法:**

```html
callbacks.lock()

```

**返回值:**这个方法返回它所附着的回调对象。

**示例 1:** 本示例首先添加并激发函数，然后锁定回调列表，然后再次添加并激发函数。

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
        JQuery | callbacks.lock() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        var el_down = document
                .getElementById("GFG_DOWN");

        var res = "";
        var callbacks = jQuery.Callbacks();
        function Geeks() {
            var func = function (val) {
                res = res + 
                    "value passed is - " + val;
            };

            // Function added to list
            callbacks.add(func);
            callbacks.fire("gfg_1");

            // Locking the callback list
            callbacks.lock(); 

            // Function again added to list
            callbacks.add(func); 
            callbacks.fire("gfg_2");
            el_down.innerHTML = res;
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/49f06d57e0bc6380abb3219e2c7e6b2d.png)

**示例 2:** 本示例提供了一个按钮，用于锁定列表，然后添加并激发函数，以检查方法是否工作。

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
        JQuery | callbacks.lock() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <button onclick="lock();">
        lock here
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        var el_down = document
                .getElementById("GFG_DOWN");

        var res = "";
        var callbacks = jQuery.Callbacks();
        function lock() {
            callbacks.lock();
        }
        function Geeks() {

            // Function to be added to the list
            var fun = function (val) {
                res = res + "This is function and "
                + "value passed is " + val + "<br>";
            };

            callbacks.add(fun); // Adding
            callbacks.fire("GFG_1");
            el_down.innerHTML = res;
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/cebb23eed9edf121c3cb42360bb33d40.png)