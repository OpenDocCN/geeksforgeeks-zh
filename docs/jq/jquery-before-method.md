# jQuery | before()方法

> 原文:[https://www.geeksforgeeks.org/jquery-before-method/](https://www.geeksforgeeks.org/jquery-before-method/)

jQuery 中的 **before()方法**用于在选中的元素前添加内容。

**语法:**

```html
$(selector).before( content, function(index) )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **内容:**此参数保存要在元素前插入的内容。内容的可能值可以是 HTML 元素、DOM 元素、jQuery 元素。
*   **函数(index):** 是可选参数，用于指定返回元素前要插入内容的函数，index 返回元素的索引定位。

**示例 1:** 本示例在元素前插入内容。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        jQuery before() Method
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <!-- Script to insert element before button element -->
    <script>
        $(document).ready(function() {
            $("button").click(function() {
                $("button").before("<p>GeeksforGeeks:"
                + " A computer science portal</p>");
            });
        });
    </script>
</head>

<body>
    <button>Click Here to Insert element before button</button>
</body>

</html>     
```

**之前点击按钮:**
![](img/fe292f0a490847f45fd4bcf70103fd09.png)
**之后点击按钮:**
![](img/0c9bd49aa5fcf1df986706b69a8eaf00.png)

**示例 2:** 本示例在指定元素之前插入内容。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        jQuery before() Method
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <!-- Script to add content before the element -->
    <script>
        $(document).ready(function(){
            $("button").click(function(){
                $("span").before("<span>GeeksforGeeks: </span>");
            });
        });
    </script>
</head>

<body>
    <span>A computer science portal for geek</span><br>

    <span>A computer science portal for geek</span><br>

    <span>A computer science portal for geek</span><br>

    <button>Click to insert</button>
</body>

</html>
```

**之前点击按钮:**
![](img/047dc989d619a014a747717f1a0c7848.png)
**之后点击按钮:**
![](img/4320e0435c7320a07c343708580363d9.png)