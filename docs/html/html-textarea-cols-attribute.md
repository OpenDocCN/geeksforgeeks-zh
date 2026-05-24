# HTML | textarea cols Attribute

> 原文：[https://www.geeksforgeeks.org/html-textarea-cols-attribute/](https://www.geeksforgeeks.org/html-textarea-cols-attribute/)

The **HTML <textarea> cols Attribute** is used to *tell the browser how many average-width characters should fit on a single line i.e the number of columns to display*.
It is used to specify the visible width of the **<Textarea>** Element.

**Syntax:**

```html
<textarea cols="number">

```

**Attribute Values:** It contains the value i.e **number** which specifies the width of the Textarea. It has a Default value which is 20.

**Example:**

```html
<!-- HTML program to illustrate cols attribute -->

<!DOCTYPE html>
<html>

<head>
    <title>
      HTML Textarea cols Attribute
  </title>
    <style>
        h1,
        h2 {
            text-align: center;
        }
    </style>
</head>

<body style="text-align:center;">
    <h1 style="color: green;"> 
            GeeksforGeeks 
        </h1>

    <h2> 
        HTML <textarea>cols Attribute 
      </h2>

    <!-- Below textarea is 
        assigned a cols value 25 
            That is, 25 characters
          will fit in a line -->
    <textarea rows="4" 
              cols="25">
        A computer science portal for geeks.
    </textarea>
</body>

</html>
```

**Output :**
![](img/33382f4ceacb8d8d165b32f6a096191a.png)

**Supported Browsers:** The browser supported by **HTML <Textarea> cols Attribute** are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Opera
*   Safari