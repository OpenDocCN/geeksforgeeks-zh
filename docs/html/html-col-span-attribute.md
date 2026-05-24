# HTML | 跨度属性

> 原文:[https://www.geeksforgeeks.org/html-col-span-attribute/](https://www.geeksforgeeks.org/html-col-span-attribute/)

**HTML < col > span 属性**用于*指定 col 元素应该跨越多少个*。

**语法:**

```html
<col span="number">
```

**属性值:**它包含指定列元素应该跨越的数量的数值。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      HTML col span Attribute
  </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML col span Attribute</h2>

    <table border="1">
        <colgroup>
            <col span="2" 
                 style="background-color:green">
                <col style="background-color:blue">
        </colgroup>
        <tr>
            <th>Name</th>
            <th>Branch</th>
            <th>Expenses</th>
        </tr>

        <tr>
            <td>BITTU</td>
            <td>CSE</td>
            <td>2500.00</td>
        </tr>

        <tr>
            <td>RAKESH</td>
            <td>ECE</td>
            <td>1400.00</td>
        </tr>
    </table>
</body>

</html>
```

**输出:**
![](img/e1628a3e840e3b1eac604e3d72b5bbc6.png)

**支持的浏览器:**T2 HTML<col>span 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧