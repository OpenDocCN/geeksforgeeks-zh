# jQuery | index()带示例

> 原文:[https://www.geeksforgeeks.org/jquery-index-with-examples/](https://www.geeksforgeeks.org/jquery-index-with-examples/)

**索引()**是 jQuery 中的一个内置方法，用于返回指定元素相对于选择器的索引。
**语法:**

```html
$(selector).index(element)

```

**参数:**接受一个可选参数“元素”，用来获取元素的位置。
**返回值:**返回表示指定元素索引的整数。

<center>**jQuery code to show the working of index() function:**</center>

**Code #1:**

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        <!--jQuery code to demonstrate index function -->

        // document ready
        $(document).ready(function() {
            // if the list is clicked
            $("li").click(function() {
                // index() 
                // to return the index of the clicked
                // element of the list
                document.getElementById("demo").innerHTML = "Clicked Index "
                                                            + $(this).index();
            });
        });
    </script>
</head>

<body>

    <p>Click on the elements of the list to display their index
       number with respect to the other elements in the list.</p>

    <ul>
        <li>Geeks</li>
        <li>for</li>
        <li>Geeks</li>
    </ul>

    <p id="demo"></p>
</body>

</html>
```

**输出:**
在点击列表中的任何元素之前

```html
单击列表中的元素，显示它们相对于列表中其他元素的索引号。

```

*   奇葩
*   为
*   奇葩

点击“办理”后-

```html
单击列表中的元素，显示它们相对于列表中其他元素的索引号。
```

*   奇葩
*   为
*   奇葩

Clicked Index 1

**代码#2:**

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        <!--jQuery code to demonstrate index function -->

        // document ready
        $(document).ready(function() {
            // if the list is clicked
            $("li").click(function() {
                // index() 
                // to return the index of the clicked
                // element of the list
                document.getElementById("demo").innerHTML = "Clicked Index "
                                    + $($(".myclass")).index($("#id"));
            });
        });
    </script>
</head>

<body>

    <p>Click on the elements of the list to display their index
       number with respect with the other elements in the list.</p>

    <ul>
        <li>Geeks</li>
        <li class="myclass">for</li>
        <li class="myclass" id="id">Geeks</li>
    </ul>

    <p id="demo"></p>
</body>

</html>
```

**输出:**
在点击列表中的任何元素之前-

```html
单击列表中的元素，显示它们相对于列表中其他元素的索引号。
```

*   奇葩
*   为
*   奇葩

点击列表中的任何元素后-

```html
单击列表中的元素，显示它们相对于列表中其他元素的索引号。
```

*   奇葩
*   为
*   奇葩

Clicked Index 1