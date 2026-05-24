# HTML | td headers Attribute

> 原文：[https://www.geeksforgeeks.org/html-td-headers-attribute/](https://www.geeksforgeeks.org/html-td-headers-attribute/)

The **HTML <td> headers Attribute** is used to *specify the table cell containing Header information for the current data cell*.

**Syntax:**

```html
<td headers="header_id">
```

**Attribute Values:** It contains the value i.e **header_id** which specify the space to the separated list of id’s to one or more Header cell that the table data cell is related to.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        table,
        th,
        td {
            border: 1px solid green;
        }
    </style>
</head>

<body>

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2> 
        HTML <td> Headers Attributes 
    </h2>

    <table>
        <tr>
            <th id="name">Name</th>
            <th id="father">Father's Name</th>
            <th id="mother">Mother's Name</th>
            <th id="phone">Phone No.</th>
        </tr>
        <tr>
            <td headers="name">Krishna</td>
            <td headers="father">Manoj Gupta</td>
            <td headers="mother">Manisha Gupta</td>
            <td headers="phone">12345</td>
        </tr>
    </table>
    <br>
</body>

</html>
```

**Output:**
![](img/a2f46ae069ef53889341d036b69b53e6.png)

**Supported Browsers:** The browsers supported by **HTML <td> headers Attribute** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Apple Safari
*   Opera