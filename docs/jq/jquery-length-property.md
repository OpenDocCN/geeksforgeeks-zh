# jQuery |长度属性

> 原文:[https://www.geeksforgeeks.org/jquery-length-property/](https://www.geeksforgeeks.org/jquery-length-property/)

**长度**属性用于统计 jQuery 对象的元素数量。

**语法:**

> $(选择器)。长度

其中选择器是要计算其长度的对象。

**返回值:**返回选择器的长度。

下面是显示 jQuery length 属性的工作示例:

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("button").click(function() {
                document.getElementById("Geeks").innerHTML = 
                                        "<br>" + $("p").length
            });
        });
    </script>
</head>

<body>

    <p style="color:green"> GeeksforGeeks</p>
    <p style="color:green">Sudo</p>
    <p style="color:green">Code</p>
    <p style="color:green">Gate</p>

    <button>Click on the button to get 
    the number of "p" elements</button>

    <div id="Geeks"></div>

</body>

</html> 
```

**输出:**
点击按钮前:
![](img/5a617910550a42069cf2be23cfc10666.png)

点击按钮后:

![](img/d3fb11085a08edc294d75e948521df44.png)