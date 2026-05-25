
# HTML | th headers Attribute

> 原文：[https://www.geeksforgeeks.org/html-th-headers-attribute/](https://www.geeksforgeeks.org/html-th-headers-attribute/)

The **HTML `<th>` headers Attribute** is used to *specify the table cell containing Header information for the current header cell*.

**Syntax:**

```html
<th headers="header_id">
```

**Attribute Values:** It contains the value i.e. **header_id** which specifies the space-separated list of ids to one or more Header cells that the table header cell is related to.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>

<!-- style to set border -->
    <style>
        table,
        th,
        td {
            border: 1px solid black;
        }
    </style>
</head>

<body>

<h1>GeeksforGeeks</h1>

<h2>HTML <th>headers Attribute</h2>

<table>
        <tr>
            <th id="table" colspan="3">Username</th>
        </tr>

<tr>
            <th headers="Username">geeks</th>
            <th headers="Username">For</th>
            <th headers="Username">Geeks</th>
        </tr>
    </table>
</body>

</html>
```

**Output:**
![](img/64fc360cb0b53926ed5422eedb9b6961.png)

**Supported Browsers:** The browsers supported by **`<th> headers Attribute`** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Apple Safari
*   Opera
