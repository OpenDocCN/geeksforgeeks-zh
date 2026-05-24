# HTML | tbody char 属性

> 原文:[https://www.geeksforgeeks.org/html-tbody-char-attribute/](https://www.geeksforgeeks.org/html-tbody-char-attribute/)

**HTML 正文字符属性**用于指定与正文元素中内容的字符对齐。仅当 align 属性设置为“char”时，才能使用该属性。它的默认值是页面语言的小数点。HTML 5 不支持。

**语法:**

```html
<tbody char="character">
```

**属性值:**

*   **字符:**用于指定要对齐内容的字符。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>html tbody char Attribute </title>
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
        <h2> HTML tbody char Attribute</h2>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>User Id</th>
                </tr>
            </thead>

            <!-- tbody tag starts from here -->
            <tbody align="char" char="." charoff="2">
                <tr>
                    <td>Shashank</td>
                    <td>@shashankla</td>
                </tr>
                <tr>
                    <td>GeeksforGeeks</td>
                    <td>@geeks</td>
                </tr>
            </tbody>
            <!-- tbody tag ends here -->

        </table>
    </center>
</body>

</html>
```

**输出:**
![](img/95dfb7ce35dbf83515a125430639b719.png)

**支持的浏览器:****HTML 表体字符属性**支持的浏览器如下:

*   不支持谷歌浏览器
*   *不支持 internet Explorer*
*   **火狐*不支持***
*   **苹果 Safari *不支持***
*   **不支持歌剧**