# jQuery |效果展示()方法

> 原文:[https://www.geeksforgeeks.org/jquery-effect-show-method/](https://www.geeksforgeeks.org/jquery-effect-show-method/)

jQuery 中的 **show()方法**用于显示隐藏和选中的元素。

**注意:**此方法显示使用 CSS 显示的隐藏元素:无属性。可见性隐藏的元素不可见。

**语法:**

```html
$(selector).show( speed, easing, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **速度:**为可选参数，用于指定淡入淡出效果的速度。速度的默认值是 400 毫秒。速度的可能值有:
    *   毫秒
    *   “慢”
    *   “快”
*   **缓和:**是可选参数，用于指定元素到动画不同点的速度。宽松的默认值是“摇摆”。宽松政策的可能价值是:
    *   “摇摆”
    *   “线性”
*   **回调:**为可选参数。在 show()方法完成后执行回调函数。

以下示例说明了 jQuery 中的 show()方法:

**示例 1:** 该示例显示显示:没有给定速度的内容。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        jQuery Effect show() Method
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
        Show
    </button> 

    <!-- Script to show display:none content -->       
    <script> 
        $(document).ready(function() {
            $("#btn").click(function() {
                $("#Outer").show(1000);
            });
        });
    </script> 
</body>  

</html> 
```

**输出:**

*   **之前点击按钮:**
    ![](img/e914e57f34719b8f99155e6203c5f5cd.png)
*   **点击按钮后:**
    ![](img/6ea3526e9ea58e52dcefe795195c9ca2.png)

**示例 2:** 该示例显示显示:不满足于挥杆放松值。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        jQuery Effect show() Method
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
        Show
    </button> 

    <!-- Script to show display: none content
            with swing easing -->     
    <script> 
        $(document).ready(function() {
            $("#btn").click(function() {
                $("#Outer").show("swing");
            });
        });
    </script> 
</body>  

</html> 
```

**输出:**

*   **之前点击按钮:**
    ![](img/e914e57f34719b8f99155e6203c5f5cd.png)
*   **点击按钮后:**
    ![](img/6ea3526e9ea58e52dcefe795195c9ca2.png)