# jQuery 回调. has()方法

> 原文:[https://www.geeksforgeeks.org/jquery-callbacks-has-method/](https://www.geeksforgeeks.org/jquery-callbacks-has-method/)

jQuery 中的**回调. has()** 方法用于回答列表是否有任何附加的回调。如果回调作为参数传递，那么它会回答它是否在列表中。

**语法:**

```html
callbacks.has([callback])

```

**参数:**

*   **回调:**参数定义要搜索的回调，在列表中。

**返回值:**该方法返回真或假。

**示例 1:** 此示例返回“true”，因为列表中有“func”。

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
        JQuery | callbacks.has() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG"></p>

    <script>
        var el_down = document.getElementById("GFG");
        var res = "";
        var callbacks = jQuery.Callbacks();

        function Geeks() {
            var func = function (val) {
                res = res + "value passed is - " + val;
            };
            callbacks.add(func); // function added to list
            callbacks.fire("gfg_1");
            el_down.innerHTML = callbacks.has();
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/d4e2ff1251e9af9b8a95812de78766bf.png)

**示例 2:** 此示例返回“false”，因为“func2”不在列表中。

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
        JQuery | callbacks.has() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        var el_down = document.getElementById("GFG_DOWN");
        var res = "";
        var callbacks = jQuery.Callbacks();

        function Geeks() {
            var func1 = function (val) {
                res = res + "value passed is - " + val;
            };
            var func2 = function (val) {
                res = res + "value passed is - " + val;
            };

            // Function added to list
            callbacks.add(func1); 
            callbacks.fire("gfg_1");
            el_down.innerHTML = callbacks.has(func2);
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/7bf6f3aec7d558180c9fd590b16dcb12.png)