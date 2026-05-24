# HTML | td nowrap Attribute

> 原文：[https://www.geeksforgeeks.org/html-td-nowrap-attribute/](https://www.geeksforgeeks.org/html-td-nowrap-attribute/)

The **HTML <td> nowrap Attribute** is used to specify that the content present inside the cell should not wrap. It contains the Boolean value. It is not supported by HTML 5.

**Syntax:**

```html
<td nowrap>
```

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML nowrap Attribute</title>
    <style>
        table,
        th,
        td {
            border: 1px solid black;
            border-collapse: collapse;
            padding: 6px;
        }
    </style>
</head>

<body style="text-align:center">

    <h1 style="color: green;">GeeksforGeeks</h1>
    <h2>HTML <td>nowrap Attribute</h2>
    <center>
        <table>
            <tr>
                <th>Name</th>
                <th>Age</th>
            </tr>
            <tr>
                <td nowrap>Ajay</td>
                <!-- This cell will take up space on 
                    two rows -->
                <td rowspan="2">24</td>
            </tr>
            <tr>
                <td>Priya</td>
            </tr>
        </table>
    </center>

</body>

</html>
```

**Output:**
![](img/7f54cf79bb263bd52bd2b0f7b75ee2e8.png)

**Supported Browsers:** The browsers supported by **HTML <td> nowrap Attribute** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Apple Safari
*   Opera