# JQuery sub()方法

> 原文:[https://www.geeksforgeeks.org/jquery-sub-method/](https://www.geeksforgeeks.org/jquery-sub-method/)

JQuery 中的 **sub()方法**用于将字符串显示为下标文本。此方法返回嵌入在标签中的字符串，如下所示:
*<子>字符串</子>T4】*

**语法:**

```html
string.sub()

```

下面讨论两个例子:

*   **例 1:**

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | sub() method
        </title>      
        <script src=
    "https://code.jquery.com/jquery-3.5.0.js">
        </script> 
    </head>   
    <body style="text-align:center;"> 
        <h1 style="color:green;">  
            GeeksForGeeks  
        </h1> 
        <p id="GFG_UP"> 
        </p>
        <button onclick="Geeks()"> 
            Click here 
        </button>       
        <p id="GFG_DOWN"> 
        </p>       
        <script> 
            var el_up = document.getElementById("GFG_UP");
            var el_down = document.getElementById("GFG_DOWN");
            var str = "Hello Geeks!";
            el_up.innerHTML = "JQuery | sub() method";
            function Geeks() {
                el_down.innerHTML = "Result is " + str.sub();
            } 
        </script> 
    </body>   
    </html>  
    ```

*   **输出:**
    ![](img/2841724c255881939c32ff71794d6b23.png)

*   **例 2:**

    ```html
    <!DOCTYPE HTML> 
    <html>  
    <head> 
        <title> 
          JQuery | sub() method
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
        <button onclick="Geeks()"> 
            Click here 
        </button>       
        <p id="GFG_DOWN"> 
        </p>       
        <script> 
            var el_up = document.getElementById("GFG_UP");
            var el_down = document.getElementById("GFG_DOWN");
            var str = "Hello Geeks!";
            el_up.innerHTML = "JQuery | sub() method";
            function Geeks() {
                el_down.innerHTML = 
    "Some text " + str.sub() + " Some other text";
            } 
        </script> 
    </body>   
    </html> 

    ```

*   **输出:**
    ![](img/d3196b419416fd6ba3c589b712327b7e.png)