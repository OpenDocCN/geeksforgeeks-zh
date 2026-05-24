# jQuery | Misc toArray()方法

> 原文:[https://www.geeksforgeeks.org/jquery-misc-toarray-method/](https://www.geeksforgeeks.org/jquery-misc-toarray-method/)

jQuery 中的 **toArray()方法**用于将 jQuery 选择器匹配的元素作为数组返回。

**语法**

```html
$(selector).toArray()
```

**参数:**此方法不接受任何参数。

**例 1:** 该方法使用 toArray()方法以数组的形式显示段落。

```html
<!DOCTYPE html>
<html>

<head> 
    <title>
        jQuery Misc toArray() Method
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head> 

<body style="text-align:center;">

    <h1 style = "color:green;" >  
        GeeksForGeeks
    </h1>  

    <h2>jQuery Misc toArray() Method</h2>

    <button>Click</button>

    <p>Geeks1</p>
    <p>Geeks2</p>
    <p>Geeks3</p>

    <!-- Script to use toArray() method -->
    <script>
        $(document).ready(function() {
            $("button").click(function() {
                var i;
                var x = $("p").toArray()
                for (i = 0; i< x.length; i++) {
                    alert(x[i].innerHTML);
                }
            });
        });
    </script>
</body>

</html>  
```

**输出:**

*   **之前点击按钮:**
    ![](img/76dac1a6db4eb5387d1ac0634ea7313f.png)
*   **点击按钮后:**
    ![](img/b4cfbf3c116730b12057860096f1ed15.png)
    ![](img/f702045129d6da99663083d83a3d8b27.png)
    ![](img/f8ef5d02364e0613b9746edd72ebb3cc.png)

**示例 2:** 本示例使用 toArray()方法显示数组元素。

```html
<!DOCTYPE html>
<html>

<head> 
    <title>
        jQuery Misc toArray() Method
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head> 

<body style="text-align:center">

    <h1 style="color:green;">  
        GeeksForGeeks
    </h1>  

    <h2>jQuery Misc toArray() Method</h2>

    <button>Click</button>

    <p>Geeks1-Geeks2-Geeks3</p>

    <div style="color:lightgreen;"></div>

    <!-- This example use toArray() method -->
    <script>
        $(document).ready(function(){
            $("button").click(function(){
                var i;
                var x = $("p").toArray()
                for (i = 0; i< x.length; i++) {
                    $("div").text(x[i].innerHTML);
                }
            });
        });
    </script>
</body>

</html>  
```

**输出:**

*   **之前点击按钮:**
    ![](img/49fa133ef526597a4086b74c58efd351.png)
*   **点击按钮后:**
    ![](img/061f74aa27d3878ca3466cd0803b7db9.png)