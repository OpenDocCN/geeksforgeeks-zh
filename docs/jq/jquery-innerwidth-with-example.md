# jQuery | innerWidth()带示例

> 原文:[https://www . geeksforgeeks . org/jquery-inner width-with-example/](https://www.geeksforgeeks.org/jquery-innerwidth-with-example/)

**innerWidth** 是 jQuery 中的一个内置方法，用于返回第一个匹配元素的宽度。
**语法:**

```html
$(selector).innerWidth()

```

这里选择器是被选择的元素。
**参数:**不接受任何参数。
**返回值:**返回选择器的宽度。
**显示 innerWidth()工作方式的 jQuery 代码:**

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        <!--jQuery code to demonstrate innerWidth function -->

        // document ready
        $(document).ready(function() {
            // on clicking the paragraph
            $("p").click(function() {
                // innerWidth
                document.getElementById("demo").innerHTML = "innerWidth = "
                                              + $("div").innerWidth();
            });
        });
    </script>
</head>

<body>

    <div style="height: 100px;width: 200px; background-color: blue">

    </div>
    <p>Click here to know innerWidth</p>
    <p id="demo"></p>
</body>

</html>
```

**输出:**
**点击前一段-**
![](img/1664a5b23d7c865c1ec7a12f4b6ba45a.png)

**点击后段落-**
![](img/c1a6c27ef170dd3417acd031940484c3.png)