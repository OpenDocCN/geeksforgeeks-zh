# HTML | DOM 表格行集合

> 原文:[https://www . geesforgeks . org/html-DOM-table-rows-collection/](https://www.geeksforgeeks.org/html-dom-table-rows-collection/)

**表格行集合**用于*返回表格中所有< tr >元素*的集合。 **< tr >** 元素的顺序与它们在源代码中的位置排序相同。

**语法**

```html
tableObject.rows
```

**属性**

*   **长度:**用于返回集合中< tr >元素的个数。

**方法**

*   **【索引】:**用于从集合中返回具有指定索引的< tr >元素。
*   **项(索引):**也用于从集合中返回具有指定索引的< tr >元素。
*   **name item(id):**它也用于从集合中返回具有指定 id 的< tr >元素。

下面的程序说明了表格行集合:
**示例:**找出表格中的行数。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Table rows Collection in HTML
  </title>
    <style>
        table,
        td {
            border: 1px solid green;
        }

        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Table rows Collection</h2>

    <p>To return the number of rows in the table,
      double-click the "Return Count" button.</p>

    <table id="Courses" align="center">
        <caption>Courses by Geeksforgeeks</caption>
        <tr>
            <td>Java</td>
            <td>Fork Java</td>
        </tr>
        <tr>
            <td>Python</td>
            <td>Fork Python</td>
        </tr>
        <tr>
            <td>Placements</td>
            <td>Sudo Placement</td>
        </tr>
    </table>
    <br>

    <button ondblclick="tr()">Return Count</button>

    <p id="test"></p>

    <script>
        function tr() {

            // number of rows.
            var c = document.getElementById(
              "Courses").rows.length;
            document.getElementById("test").innerHTML = 
              c + " Rows are present in the table.";
        }
    </script>

</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/1a269dbec980011aeec334e3c5b836bd.png)

**点击按钮后:**
![](img/cf58486783709544afd86758202c2d0f.png)

**支持的浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧