# jQuery | ajaxSend()方法

> 原文:[https://www.geeksforgeeks.org/jquery-ajaxsend-method/](https://www.geeksforgeeks.org/jquery-ajaxsend-method/)

jQuery 中的 **ajaxSend()方法**用于指定当 **AJAX 请求即将发送时要运行的函数。**

**语法:**

```html
$(document).ajaxSend( function(event, xhr, options) )
```

**参数:**该方法接受单参数函数，该函数是强制的。该函数接受三个参数，如上所述，如下所述:

*   **事件:**保存事件对象。
*   **xhr:** 它保存 XMLHttpRequest 对象。
*   **选项:**保存 AJAX 请求中使用的选项。

存储在服务器上的 demo.txt 文件，点击**更改内容**按钮后加载。
T3

```html
This is GFG.
```

**示例 1:** 本示例通过从服务器获取数据来更改< p >元素的内容。当 AJAX 请求准备发送时，页面显示 **AJAX 请求即将发送**。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <script src= 
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"> 
        </script> 

        <!-- Script to use ajaxSend() method -->
        <script> 
            $(document).ready(function() {
                $(document).ajaxSend(function() {
                    alert("AJAX request is about to send");
                });

                $("button").click(function() {
                    $("#paragraph").load("demo.txt");
                });
            });
        </script> 
    </head> 

    <body style="text-align:center;"> 

        <div id="div_content"> 

            <h1 style = "color: green;">
                GeeksforGeeks
            </h1> 

            <p id = "paragraph" style= "font-size: 20px;">
                A computer science portal for geeks
            </p> 
        </div>

        <button>
            Change Content
        </button> 
    </body> 
</html>                    
```

**输出:**

*   **之前点击按钮:**
    ![](img/1ee67ae947c139820a9d06c6a549bef4.png)
*   **点击按钮后:**
    ![](img/79ed81a9190c0099aa30ab18d4b53b78.png)
    ![](img/c65ebd13ffd719ce68501a04c88e0bf6.png)

**示例 2:** 本示例通过从服务器获取数据来更改< h1 >元素的内容。当 AJAX 请求准备发送时，页面显示 **AJAX 请求即将发送**。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <script src= 
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"> 
        </script> 

        <!-- Script to use ajaxSend() method -->
        <script> 
            $(document).ready(function() {
                $(document).ajaxSend(function() {
                    alert("AJAX request is about to send");
                });

                $("button").click(function() {
                    $("#heading").load("demo.txt");
                });
            });
        </script> 
    </head> 

    <body style="text-align:center;"> 

        <div id="div_content"> 

            <h1 id = "heading" style = "color: green;">
                GeeksforGeeks
            </h1> 

            <p style= "font-size: 20px;">
                A computer science portal for geeks
            </p> 
        </div> 

        <button>
            Change Content
        </button> 
    </body> 
</html>                    
```

**输出:**

*   **之前点击按钮:**
    ![](img/1ee67ae947c139820a9d06c6a549bef4.png)
*   **点击按钮后:**
    ![](img/79ed81a9190c0099aa30ab18d4b53b78.png)
    ![](img/d7fcd19220c47a950081ca52ec877343.png)