# HTML | th width Attribute

> 原文：[https://www.geeksforgeeks.org/html-th-width-attribute/](https://www.geeksforgeeks.org/html-th-width-attribute/)

The **HTML <th> width Attribute** is used to *specify the width of a table header cell*. If width attribute is not set then it takes default width according to content. It is not supported by HTML 5.

**Syntax:**

```html
<th width="pixels | %">
```

**Attribute Values:**

*   **pixels:** It sets the width of table header cell in terms of pixels.
*   **%:** It sets the width of table header cell in terms of percentage (%).

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML th width Attribute
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML th width Attribute</h2>

    <table border="1" width="500">
        <tr>
            <th width="50%">NAME</th>
            <th width="20%">AGE</th>
            <th width="30%">BRANCH</th>
        </tr>

        <tr>
            <td>BITTU</td>
            <td>22</td>
            <td>CSE</td>
        </tr>

        <tr>
            <td>RAKESH</td>
            <td>25</td>
            <td>EC</td>
        </tr>
    </table>
</body>

</html>
```

**Output:**
![](img/3f01e93b4f5ff03cc884f4daba55189d.png)

**Supported Browsers:** The browser supported by **HTML <th> width attribute** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera