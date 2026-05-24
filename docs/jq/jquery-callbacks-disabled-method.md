# jQuery 回调. disabled()方法

> 原文:[https://www . geesforgeks . org/jquery-回调-禁用-方法/](https://www.geeksforgeeks.org/jquery-callbacks-disabled-method/)

jQuery **回调. disabled()** 方法用于检查回调是否被禁用。该方法根据回调返回“真”或“假”。

**语法:**

```html
callbacks.disabled()
```

**返回值:**这个方法返回一个布尔值。

**示例 1:** 本示例禁用回调，然后调用**回调. disabled()** 方法查看结果。

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        jQuery callbacks.disabled() method
    </title>

    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

    <p id="GFG_UP"></p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        var el_up = document.getElementById("GFG_UP");
        var el_down = document.getElementById("GFG_DOWN");
        el_up.innerHTML = 
            "JQuery | callbacks.disabled() method";

        var result = "";
        var callbacks = jQuery.Callbacks();

        function Geeks() {

            // First function to be added to the list
            var fun1 = function (val) {
                result = result + "This is function 1 and"
                    + " value passed is " + val + "<br>";
            };

            callbacks.add(fun1); // Adding the function 1
            callbacks.fire("GFG_1"); // Calling the function 1
            callbacks.disable();
            el_down.innerHTML = callbacks.disabled();
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/3df4d43d9b32e53cbb65eb3e56def94d.png)

**示例 2:** 本示例提供了一个*按钮*来禁用回调，然后进行检查。

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        jQuery callbacks.disabled() method
    </title>

    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

    <p id="GFG_UP"></p>

    <button onclick="Geeks();">
        click here
    </button>

    <button onclick="disable();">
        disable
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        var el_up = document.getElementById("GFG_UP");
        var el_down = document.getElementById("GFG_DOWN");
        el_up.innerHTML = 
                "JQuery | callbacks.disabled() method";
        var result = "";
        var callbacks = jQuery.Callbacks();
        function disable() {
            callbacks.disable();
        }
        function Geeks() {

            // First function to be added to the list
            var fun1 = function (val) {
                result = result + "This is function 1 and"
                    + " value passed is " + val + "<br>";
            };
            callbacks.add(fun1); // Adding the function 1
            callbacks.fire("GFG_1"); // Calling the function 1
            el_down.innerHTML = callbacks.disabled();
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/7606a92ddc5d2cf02e6616779a49bf49.png)