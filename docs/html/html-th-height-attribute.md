# HTML | th height Attribute

> 原文：[https://www.geeksforgeeks.org/html-th-height-attribute/](https://www.geeksforgeeks.org/html-th-height-attribute/)

The **HTML <th> height Attribute** is used to *specify the height of the table header cell*. If the **<th>** height attribute is not set then it takes default height according to content. It is not supported by HTML 5.

**Syntax:**

```html
<th height="pixels | %">
```

**Attribute Values:**

*   **pixels:** It sets the height of table header cell in terms of pixels.
*   **%:** It sets the height of table header cell in terms of percentage (%).

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML th height Attribute
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML th height Attribute</h2>

    <table border="1" width="500">
        <tr>
            <th height="50">NAME</th>
            <th height="50">AGE</th>
            <th height="50">BRANCH</th>
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
![](img/6fabd2db77a73af310deca0e1998b8e9.png)

**Supported Browsers:** The browser supported by **HTML <th> height attribute** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera