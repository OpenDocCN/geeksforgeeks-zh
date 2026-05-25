# jQuery :even 选择器

> 原文: [https://www.geeksforgeeks.org/jquery-even-selector/](https://www.geeksforgeeks.org/jquery-even-selector/)

`jQuery :even` 选择器用于从匹配元素中选择偶数索引。索引号从 0 开始。其工作原理与 `:odd` 选择器相同，但选择的是偶数索引。

## 语法

```html
$(":even")
```

### 示例 1

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("tr:even").css("background-color", "green");
        });
    </script>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <table border="1">
            <tr>
                <th>Company</th>
                <th>Country</th>
            </tr>
            <tr>
                <td>reliance</td>
                <td>India</td>
            </tr>
            <tr>
                <td>flipkart</td>
                <td>India</td>
            </tr>
            <tr>
                <td>walmart</td>
                <td>American</td>
            </tr>
            <tr>
                <td>Ernst Handle</td>
                <td>Austria</td>
            </tr>
            <tr>
                <td>Island Trading</td>
                <td>UK</td>
            </tr>
        </table>
    </center>
</body>

</html>
```

**输出:**

![](img/314737204c97ee5c51e1c16564ad0ed6.png)

### 示例 2

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("tr:even").css("background-color", "lightgreen");
        });
    </script>
</head>

<body>
    <center>
        <h1>Welcome To GeeksForGeeks</h1>
        <table border="2">
            <tr>
                <th>State</th>
                <th>Capital</th>
            </tr>
            <tr>
                <td>uttar pradesh</td>
                <td>lucknow</td>
            </tr>
            <tr>
                <td>punjab</td>
                <td>chandigarh</td>
            </tr>
            <tr>
                <td>haryana</td>
                <td>candigarh</td>
            </tr>
        </table>
    </center>
</body>

</html>
```

**输出:**

![](img/984e86b441ec07eceab8cb90ad5d3bd0.png)

## 支持的浏览器

*   Google Chrome 90.0+
*   Internet Explorer 9.0
*   Firefox 3.6
*   Safari 4.0
*   Opera 10.5