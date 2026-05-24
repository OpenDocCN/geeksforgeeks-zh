# JQuery hasData()方法

> 原文:[https://www.geeksforgeeks.org/jquery-hasdata-method/](https://www.geeksforgeeks.org/jquery-hasdata-method/)

jQuery 中的这个 **hasData()方法**用于判断一个元素是否有任何 JQuery 数据与之关联。该数据可以是文本、与元素相关联的事件。下面讨论两个例子:

**语法:**

```html
jQuery.hasData(element)

```

**论据:**

*   **元素:**该参数是一个要检查数据的 DOM 元素。

*   **示例:**没有与< div >关联的数据，因此该方法返回 false。

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | hasData() method
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
        <div> This is DIV
        </div>
        <br>
        <button onclick="Geeks()"> 
            Click here 
        </button>       
        <p id="GFG_DOWN"> 
        </p>       
        <script> 
            var el_up = document.getElementById("GFG_UP");
            var el_down = document.getElementById("GFG_DOWN");
            var $div = jQuery( "div" ), div = $div[ 0 ];
            el_up.innerHTML = "JQuery | hasData() method";
            function Geeks() { 
                el_down.innerHTML = jQuery.hasData(div);
            } 
        </script> 
    </body>   
    </html> 
    ```

*   **输出:**
    ![](img/4bab7d22e1edf3f2eff1d189eef617de.png)

*   **示例:**有一个事件与< div >相关联，因此该方法返回 true。

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | hasData() method
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
        <div> This is DIV
        </div>
        <br>
        <button onclick="Geeks()"> 
            Click here 
        </button>       
        <p id="GFG_DOWN"> 
        </p>       
        <script> 
            var el_up = document.getElementById("GFG_UP");
            var el_down = document.getElementById("GFG_DOWN");
            var $div = jQuery( "div" ), div = $div[ 0 ];
            el_up.innerHTML = "JQuery | hasData() method";
            $div.on( "click", function() {} );
            function Geeks() { 
                el_down.innerHTML = jQuery.hasData(div);
            } 
        </script> 
    </body>   
    </html> 
    ```

*   **输出:**
    ![](img/278dbfc4fa563062318c55b2874d21fe.png)