# HTML 中“角色”属性的用途是什么？

> 原文:[https://www . geesforgeks . org/html 中角色属性的用途是什么/](https://www.geeksforgeeks.org/what-is-the-purpose-of-role-attribute-in-html/)

**角色**属性的主要目的是支持 **ARIA** ，即可访问的丰富互联网应用程序，这有助于从语义角度提供丰富性和质量。此外，**角色**属性使网站更加便利，使用该属性被认为是一种良好的做法。通常，角色对于没有定义自己角色属性的语言是必要的。

**例**:

```html
<!DOCTYPE>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>
        Output of Role Attribute
    </title>
    <style>
        h1 {
            text-align: center;
            color: green;
            font-size: 100px;
        }

        h2 {
            text-align: center;
        }
    </style>
</head>

<body role="document">
    <h1>GeeksforGeeks</h1>
    <h2>Understanding usage of "Role" Attribute</h2>
</body>

</html>
```

**输出** :

![Role Attribute Output](img/1c0c530f5fd81ddf0d26d5e5dd757809.png)

为角色属性获取的输出

输出没有显示任何值得注意的重要内容。这表明，即使代码中没有使用角色属性，也不会影响我们的代码和输出。

通过使用角色属性，我们可以获得诸如可访问性、设备适配、服务器端处理、复杂数据描述等功能，以及更多类似的功能。因此，建议使用角色属性来获得更好的代码性能。