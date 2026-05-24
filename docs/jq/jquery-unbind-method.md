# jQuery |解除绑定()方法

> 原文:[https://www.geeksforgeeks.org/jquery-unbind-method/](https://www.geeksforgeeks.org/jquery-unbind-method/)

**解除绑定()方法**是 jQuery 中的一个内置方法，用于移除任何选定的事件处理程序。此方法可用于移除特定的事件处理程序或停止特定的功能。它可以在任何使用事件对象的事件处理程序上工作。

**注意:**如果没有提供参数，该方法对指定元素的所有事件处理程序起作用。
**语法:**

```html
$(selector).unbind(event, function, eventObj)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **事件:**它是一个可选参数，用于指定事件(一个或多个)以将其从元素中移除。
*   **函数:**是一个可选参数，用于指定要从元素的指定事件中解除绑定的函数的名称。
*   **事件对象:**是一个可选参数，用于指定要从事件绑定函数中移除的事件对象。

**示例 1:** 本示例描述了 unbind()方法，用于从所选元素中移除事件处理程序。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        jQuery unbind() Method
    </title> 

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
 </head> 

 <body style = "text-align:center;">  

    <h1 style = "color:green;" >  
        GeeksForGeeks  
    </h1>  

    <button> 
        Click Here 
    </button> 

    <!-- Script to illustrates unbind() method -->
    <script>
        $(document).ready(function() {
            $("h1").click(function() {
                $(this).slideToggle();
            });

            $("button").click(function() {
                $("h1").unbind();
            });
        });
    </script>
</body>  

</html> 
```

**输出:**

*   **点击任意位置前:**
    ![](img/5e1d76d03f768bae68eb0667d57a4e6f.png)
*   **点击元素 h1 后:**
    ![](img/a87aa0f8cf4223488ac842403a0b8d9a.png)
*   **点击按钮后事件将不起作用:**
    ![](img/5e1d76d03f768bae68eb0667d57a4e6f.png)

**示例 2:** 本示例描述了 unbind()方法，用于从所选元素中移除事件处理程序。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        jQuery unbind() Method
    </title> 

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <style>
        h1 {
            border: 1px solid black;
            height: 100px;
            padding-top: 35px;
            background: green;
            color: white;
        }
    </style>
</head> 

<body style = "text-align:center;">  

    <h1>GeeksForGeeks</h1>  

    <button> 
        Remove event handler from geeks for geeks
    </button> 

    <!-- Script to illustrates unbind() method -->   
    <script>
        $(document).ready(function() {
            $("h1").click(function() {
                $(this).slideToggle();
            });

            $("button").click(function() {
                $("h1").unbind();
            });
        });
    </script>
</body>  

</html> 
```

**输出:**

*   **点击任意位置前:**
    ![](img/c55b417004dfee07c88b0a52ab14eec8.png)
*   **点击元素 h1 后:**
    ![](img/53647b21327fe56cdd3961da02bc780a.png)
*   **点击按钮后事件将不起作用:**
    ![](img/c55b417004dfee07c88b0a52ab14eec8.png)