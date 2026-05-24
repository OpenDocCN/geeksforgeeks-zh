# jQuery | fadeToggle()方法

> 原文:[https://www.geeksforgeeks.org/jquery-fadetoggle-method/](https://www.geeksforgeeks.org/jquery-fadetoggle-method/)

jQuery 中的 **fadeToggle()方法**在 fadeIn()和 fadeOut()方法之间切换。如果元素淡入，fadeToggle()将淡出。如果元素淡出，fadeToggle()将淡入。

**语法:**

```html
$(selector).fadeToggle(speed, easing, callback)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **速度:**为可选参数，用于指定淡入淡出效果的速度。速度的默认值是 400 毫秒。速度的可能值有:
    *   毫秒
    *   “慢”
    *   “快”
*   **缓和:**是可选参数，用于指定元素到动画不同点的速度。宽松的默认值是“摇摆”。宽松政策的可能价值是:
    *   “摇摆”
    *   “线性”
*   **回调:**为可选参数。回调函数在 fadeToggle()方法完成后执行。

以下示例说明了 jQuery 中的 fadeToggle()方法:

**示例 1:** 本示例在给定速度下显示 fadeToggle()方法效果。速度可以用毫秒来设定。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        jQuery fadeToggle() Method
    </title>

    <style>
        #Outer {
          border: 1px solid black;
          padding-top: 40px;
          height: 140px;
          background: green;
          display: none;
        }
    </style>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body style = "text-align:center;">  

    <div id= "Outer">
        <h1 style = "color:white;" >  
            GeeksForGeeks  
        </h1>  
    </div><br>

    <button id = "btn"> 
        Fade Toggle
    </button> 

    <!-- Script to use fadeToggle() Method -->           
    <script> 
        $(document).ready(function() {
            $("#btn").click(function() {
                $("#Outer").fadeToggle(1000);
            });
        });
    </script> 
</body>  

</html> 
```

**输出:**

*   **之前点击按钮:**
    ![](img/111151b00c48e56165545acbc44c5bd8.png)
*   **先点击按钮后:**
    ![](img/595708887e6da0450a814a25b373821b.png)
*   **秒后点击按钮:**
    ![](img/111151b00c48e56165545acbc44c5bd8.png)

**示例 2:** 本示例显示了带有挥杆放松的 fadeToggle()方法效果。缓和用于设置动画不同点的元素速度。

```html
<!DOCTYPE html>  
<html>  
    <head> 
        <title> 
            jQuery fadeToggle() Method
        </title>

        <style>
            #Outer {
                border: 1px solid black;
                padding-top: 40px;
                height: 140px;
                background: green;
                display: none;
            }
        </style>

        <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>
    </head>

    <body style = "text-align:center;">  

        <div id= "Outer">
            <h1 style = "color:white;" >  
                GeeksForGeeks  
            </h1>  
        </div><br>

        <button id = "btn"> 
            Fade Toggle
        </button> 

        <script> 
            $(document).ready(function() {
                $("#btn").click(function() {
                    $("#Outer").fadeToggle("swing");
                });
            });
        </script> 
    </body>  
</html> 
```

**输出:**

*   **之前点击按钮:**
    ![](img/111151b00c48e56165545acbc44c5bd8.png)
*   **先点击按钮后:**
    ![](img/595708887e6da0450a814a25b373821b.png)
*   **秒后点击按钮:**
    ![](img/111151b00c48e56165545acbc44c5bd8.png)