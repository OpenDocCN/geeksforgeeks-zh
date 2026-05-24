# JQuery delivered . notify()方法

> 原文:[https://www . geesforgeks . org/jquery-delivered-notify-method/](https://www.geeksforgeeks.org/jquery-deferred-notify-method/)

JQuery 中的这个**delivered . notify()**方法用于调用具有给定参数的 delivered 对象上的 progress 回调。

**语法:**

```html
deferred.notify(params)
```

**参数:**

*   **参数:**这是传递给 progress 回调的可选参数。

**返回值:**此方法方法返回延迟对象。

下面讨论两个例子:

*   **示例:**在本例中，notify()是用参数调用的。

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | deferred.notify() method
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
            el_up.innerHTML = "JQuery | deferred.notify() method";
            function Func(val, div){
              $(div).append('From function "Func": ' + val);
            }
            function Geeks() {
                var def = $.Deferred();
                def.progress(Func);
                def.notify(
    'notify() is called with arguments. <br />', '#GFG_DOWN');
            } 
        </script> 
    </body>   
    </html>       

    ```

*   **输出:**
    ![](img/d5a66882432835b5027186c18ada95b7.png)

*   **示例:**在本例中，调用 notify()时没有参数。

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | deferred.notify() method
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
            el_up.innerHTML = "JQuery | deferred.notify() method";
            function Func(val, div){
              $(div).append('From function "Func": ' + val);
            }
            function Geeks() {
                var def = $.Deferred();
                def.done(Func);
                def.progress(Func);
                def.notify();
                def.resolve('Deferred is resolved.<br />', '#GFG_DOWN')
            } 
        </script> 
    </body>   
    </html> 
    ```

*   **输出:**
    ![](img/e619ed3e04a3e50ee687648e44ba6b7d.png)