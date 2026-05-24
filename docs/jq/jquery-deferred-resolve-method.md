# JQuery delivered . resolve()方法

> 原文:[https://www . geesforgeks . org/jquery-delivered-resolve-method/](https://www.geeksforgeeks.org/jquery-deferred-resolve-method/)

JQuery 中的这个**delivered . resolve()**方法用于解析一个 delivered 对象，并使用给定的参数调用任何 done 回调。
**语法:**

```html
deferred.resolve([args])

```

**参数:**

*   **参数:**这是可选参数，是传递给 done 回调的参数。

**返回值:**该方法返回延迟对象。

下面讨论两个例子:

*   **示例:**在本例中，使用参数调用 resolve()。

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | deferred.resolve() method
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
            el_up.innerHTML = "JQuery | deferred.resolve() method";
            function Func(val, div){
              $(div).append(val);
            }
            function Geeks() {
                var def = $.Deferred();
                def.done(Func);
                def.resolve(
    'resolve() method is called with arguments 
               and Deferred object is resolved', '#GFG_DOWN')
            } 
        </script> 
    </body>   
    </html>        

    ```

*   **输出:**
    ![](img/7c8c4782ffc81619ec1162a6bdc2764f.png)

*   **示例:**在本例中，调用 resolve()时没有参数。

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | deferred.resolve() method
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
            el_up.innerHTML = "JQuery | deferred.resolve() method";
            function Func(){
              $('#GFG_DOWN').append(
    "resolve() method is called without arguments
              and Deferred object is resolved");
            }
            function Geeks() {
                var def = $.Deferred();
                def.done(Func);
                def.resolve()
            } 
        </script> 
    </body>   
    </html>
    ```

*   **输出:**
    ![](img/e8ae7f17d9ea6ee4d93722d66eed4e81.png)