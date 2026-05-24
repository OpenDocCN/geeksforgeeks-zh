# HTML | tr charoff Attribute

> 原文：[https://www.geeksforgeeks.org/html-tr-charoff-attribute/](https://www.geeksforgeeks.org/html-tr-charoff-attribute/)

The **HTML tr charoff Attribute** is used to sets the number of characters that aligned the characters specified by the char Attribute. This attribute can only be used in the char attribute and align attribute is specified in the tr Element.

**Syntax:**

```html
<tr charoff="number">
```

**Attribute Values:**

*   **number:** It contains the numeric value which specify the alignment.

1.  **Positive values:** indicate the alignment to the right of the characters.
2.  **Negative values:** indicate the alignment to the left of the characters.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>tr charoff </title>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }

        th {
            color: blue;
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
        <h2> HTML tr charoff Attribute</h2>
        <table>
            <thead>
                <!-- tr tag starts here -->
                <tr align="char" charoff=".">
                    <th>Name</th>
                    <th>User Id</th>
                </tr>
                <!-- tr tag end here -->
            </thead>
            <tbody>
                <tr>
                    <td>Shashank</td>
                    <td>@shashankla</td>
                </tr>
                <tr>
                    <td>GeeksforGeeks</td>
                    <td>@geeks</td>
                </tr>
            </tbody>
        </table>
    </center>
</body>

</html>
```

**Output:**
![](img/7b7994da6c8fbec56d3c79c26aeac803.png)

**Supported Browsers:** The browsers supported by **HTML tr charoff Attribute** are listed below:

*   Google Chrome *Not supported*
*   Internet Explorer *Not supported*
*   Firefox *Not supported*
*   Apple Safari *Not supported*
*   Opera *Not supported*