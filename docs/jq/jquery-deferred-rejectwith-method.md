# jQuery delivered . rejectwith()方法

> 原文:[https://www . geesforgeks . org/jquery-delivered-rejectwith-method/](https://www.geeksforgeeks.org/jquery-deferred-rejectwith-method/)

jQuery 中的这个**delivered . rejectwith()**方法用于拒绝一个 delivered 对象，并调用 failCallbacks 以及给定的上下文和参数。

**语法:**

```html
deferred.rejectWith(context[, args])
```

**参数:**

*   **上下文:**此参数是作为“This”对象传递给 failCallbacks 的上下文。
*   **参数:**该参数是传递给 failCallbacks 的可选参数数组。

**返回值:**该方法返回延迟对象。

**示例 1:** 在本例中，我们用两个参数拒绝延迟对象，并处理任何 failCallbacks。

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
        JQuery | deferred.rejectWith() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        function Func(val, div) {
            $(div).append(val);
        }

        function Geeks() {
            var def = $.Deferred();
            def.fail(Func);
            def.rejectWith(this, 
['Deferred is rejected by rejectWith() method.<br/>',
                '#GFG_DOWN']);
        } 
    </script>
</body>

</html> 
```

**输出:**
![](img/16b088b9a28d05172c61e0fb1f74426f.png)

**示例 2:** 在本例中，我们拒绝只有一个参数的延迟对象，并处理任何 failCallbacks。

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
        JQuery | deferred.rejectWith() method
    </p>

    <button onclick="Geeks();">
        click here
    </button>

    <p id="GFG_DOWN"></p>

    <script>
        function Func(div) {
            $(div).append(
'Deferred is rejected by rejectWith() method');
        }

        function Geeks() {
            var def = $.Deferred();
            def.fail(Func);
            def.rejectWith(this, ['#GFG_DOWN']);
        } 
    </script>
</body>

</html>  
```

**输出:**
![](img/16b088b9a28d05172c61e0fb1f74426f.png)