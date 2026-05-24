# HTML | td abbr Attribute

> 原文：[https://www.geeksforgeeks.org/html-td-abbr-attribute/](https://www.geeksforgeeks.org/html-td-abbr-attribute/)

The **HTML <td> abbr attribute** is used to *specify the shorter version of the content*. This attribute is not supported by HTML 5\. It does not describe any visual effect but it is used by screen readers.

**Syntax:**

```html
<td abbr="text">
```

**Attribute Values:**

*   **text:** It contains the short description of cell content.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      HTML td abbr Attribute
  </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML td abbr Attribute</h2>

    <table border="1">
        <tr>
            <th>NAME</th>
            <th>AGE</th>
            <th>BRANCH</th>
        </tr>

        <tr>
            <td abbr="name of student">BITTU</td>
            <td abbr="age of student">22</td>
            <td abbr="branch name">CSE</td>
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
![](img/5800ccb9ca8dc236c0350bfed87a4580.png)

**Supported Browsers:** The browser supported by HTML <td> abbr attribute are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera