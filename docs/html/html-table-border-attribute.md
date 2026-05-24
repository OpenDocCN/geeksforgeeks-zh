# HTML |表格边框属性

> 原文:[https://www.geeksforgeeks.org/html-table-border-attribute/](https://www.geeksforgeeks.org/html-table-border-attribute/)

**HTML <表格>边框属性**用于*指定表格*的边框。它设置表格单元格周围的边框。

**语法:**

```html
<table border="1|0">
```

**属性值:**

*   **1:** 设置表格单元格周围的边框。
*   **0:** 移除(未设置)表格单元格周围的边框。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML table border Attribute
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML table border Attribute</h2>

    <table border="1">
        <caption>Author Details</caption>

        <tr>
            <th>NAME</th>
            <th>AGE</th>
            <th>BRANCH</th>
        </tr>
        <tr>
            <td>BITTU</td>
            <td>22</td>
            <td>CSE</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>21</td>
            <td>ECE</td>
        </tr>
    </table>
</body>

</html>
```

**输出:**
![](img/edea8704a77b560c65d7244937a6d0d0.png)

**支持的浏览器:**以下是 **HTML <表格>边框属性**支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧