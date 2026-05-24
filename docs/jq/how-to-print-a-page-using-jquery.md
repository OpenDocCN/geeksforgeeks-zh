# 如何使用 jQuery 打印页面？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery 打印页面/](https://www.geeksforgeeks.org/how-to-print-a-page-using-jquery/)

任务是使用 jQuery 通过调用 window.print 方法在用户单击按钮时打印页面。发送 window.print()方法打开打印对话框打印当前文档。它没有任何参数值。

**例:**:

**HTML 代码:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to. print a page using jQuery.?
    </title>
</head>

<body>
    <center>
        <h1>Hello GeeksForGeeks Users</h1>

        <h3>
            How to. print a page using jQuery.?
        </h3>

        <Button id="sudo" onclick=
            "print_current_page()" />
            Print!
        </button>
    </center>
</body>

</html>
```