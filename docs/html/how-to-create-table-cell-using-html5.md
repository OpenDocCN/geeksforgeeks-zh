# 如何用 HTML5 创建表格单元格？

> 原文:[https://www . geesforgeks . org/如何使用-html5 创建表格-单元格/](https://www.geeksforgeeks.org/how-to-create-table-cell-using-html5/)

在本文中，我们将使用 HTML b 表格中的**[<>](https://www.geeksforgeeks.org/html-tr-tag/)和 [< td >](https://www.geeksforgeeks.org/html-td-tag/)** 标签的组合来创建表格中的单元格。

**语法:**

```html
<table>
  <tr>
    <td> . . . </td>
    <td> . . . </td>
  </tr>
</table>

```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to create a cell in 
        a table using HTML5?
    </title>

    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }

        table,
        tbody,
        td {
            border: 1px solid black;
            border-collapse: collapse;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <h2> 
            How to create a cell in 
            a table using HTML5?
        </h2>

        <table>

            <!-- tr tag starts here -->
            <tr>
                <td>Geeks</td>
                <td>For </td>
                <td>Geeks</td>
            </tr>
            <!-- tr tag end here -->
        </table>
    </center>
</body>

</html> 
```

**输出:**
![](img/0ca40a93ba7ac3a9d164964fc8602c6f.png)

**支持的浏览器如下:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧