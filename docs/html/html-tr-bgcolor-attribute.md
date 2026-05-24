# HTML | tr bgcolor Attribute

> 原文：[https://www.geeksforgeeks.org/html-tr-bgcolor-attribute/](https://www.geeksforgeeks.org/html-tr-bgcolor-attribute/)

The **HTML <tr> bgcolor Attribute** is used to *specify the background color of a table row*. It is not supported by HTML 5.

**Syntax:**

```html
<tr bgcolor= "color_name | hex_number | rgb_number">
```

**Attribute Values:**

*   **color_name:** It sets the background color by using the color name. For example *“red”*.
*   **hex_number:** It sets the background color by using the color hex code. For example *“#0000ff”*.
*   **rgb_number:** It sets the background color by using the RGB code. For example: “*RGB(0, 153, 0)”* .

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML tr bgcolor Attribute</title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML tr bgcolor Attribute</h2>

    <table width="500" border="1">
        <tr bgcolor="green">
            <th>Name</th>
            <th>Expenses</th>
        </tr>

        <tr bgcolor="yellow">
            <td>BITTU</td>
            <td>2500.00</td>
        </tr>

        <tr bgcolor="red">
            <td>RAKESH</td>
            <td>1400.00</td>
        </tr>
    </table>
</body>

</html>
```

**Output:**
![](img/e527e85977ec330d8ea86a6c5dfff9ae.png)

**Supported Browsers:** The browser supported by **HTML <tr> bgcolor attribute** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera