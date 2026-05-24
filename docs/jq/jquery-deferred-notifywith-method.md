# JQuery delivered . notifywith()方法

> 原文:[https://www . geesforgeks . org/jquery-delivered-notifywith-method/](https://www.geeksforgeeks.org/jquery-deferred-notifywith-method/)

JQuery 中的这个**delivered . notifywith()**方法用于调用 delivered 对象上的 progress 回调以及提供的上下文和参数。
**语法:**

```html
deferred.notifyWith(context[, args])

```

**参数:**

*   **上下文:**此参数是作为“This”对象传递给 progress 回调的上下文。
*   **参数:**该参数是传递给 progress 回调的可选参数数组。

**返回值:**该方法返回延迟对象。

下面讨论两个例子:
**例子-1:** 在这个例子中，我们用两个参数通知延迟对象，并在拒绝它之前处理任何 process 回调。

```html
<!DOCTYPE HTML> 
<html>  
<head> 
    <title> 
      JQuery | deferred.notifyWith() method
    </title>
    <script src=
"https://code.jquery.com/jquery-3.5.0.js"></script> 
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
        el_up.innerHTML = "JQuery | deferred.notifyWith() method";
        function Func(val, div){
          $(div).append('From function "Func": ' + val);
        }
        function Geeks() {
            var def = $.Deferred();
            def.progress(Func);
            def.notifyWith(
this, ['notifyWith() is called with arguments. <br />', '#GFG_DOWN']);
        } 
    </script> 
</body>   
</html>       

```

**输出:**
![](img/70e25a43664da2e16cd2310245166343.png)

**示例-2:** 在本例中，我们仅用一个参数通知延迟对象，并在解析它之前处理任何 process 回调。

```html
<!DOCTYPE HTML> 
<html>  
<head> 
    <title> 
      JQuery | deferred.notifyWith() method
    </title>
    <script src="https://code.jquery.com/jquery-3.5.0.js">
    </script> 
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
        el_up.innerHTML = "JQuery | deferred.notifyWith() method";
        function Func(val, div){
          $(div).append('From function "Func": ' + val);
        }
        function Geeks() {
            var def = $.Deferred();
            def.done(Func);
            def.progress(Func);
            def.notifyWith(this, ['#GFG_DOWN']);
            def.resolve('Deferred is resolved.<br />', '#GFG_DOWN')
        } 
    </script> 
</body>   
</html>  
```

**输出:**
![](img/d7bb046ae32315819079d56cd06cc8d6.png)