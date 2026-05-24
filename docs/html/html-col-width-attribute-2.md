# HTML | 宽度属性

> 原文:[https://www.geeksforgeeks.org/html-col-width-attribute-2/](https://www.geeksforgeeks.org/html-col-width-attribute-2/)

**HTML <栏>宽度属性**用于*指定列元素*的宽度。如果未设置宽度属性，则根据内容采用默认宽度。HTML 5 不支持。

**语法:**

```html
<col width="pixels | % | relative_length">
```

**属性值:**

*   **像素:**以像素为单位设置表格宽度。
*   **%:** 以百分比(%)设置表格宽度。
*   **relative_length:** 设置列元素的相对宽度。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML col width Attribute</title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML col width Attribute</h2>

    <table border="1">
        <col width="150">
            <col width="100">

                <tr>
                    <th>Name</th>
                    <th>Expenses</th>
                </tr>

                <tr>
                    <td>BITTU</td>
                    <td>2500.00</td>
                </tr>

                <tr>
                    <td>RAKESH</td>
                    <td>1400.00</td>
                </tr>
    </table>
</body>

</html>
```

**输出:**
![](img/1c74c164a67e8c7d8caedfc7a685f6a1.png)

**支持的浏览器:**支持的浏览器 **HTML < col >宽度属性**如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧