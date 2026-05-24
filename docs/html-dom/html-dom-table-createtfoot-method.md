# HTML | DOM 表 createTFoot()方法

> 原文:[https://www . geesforgeks . org/html-DOM-table-createtfoot-method/](https://www.geeksforgeeks.org/html-dom-table-createtfoot-method/)

**Table createTFoot()方法**用于创建一个空的 **< tfoot >** 元素，并将其添加到表格中。如果<>元素已经存在，则不会创建新的< tfoot >元素*。在这种情况下，createTFoot()方法返回现有的一个。
t foot>元素内部必须有多个< tr >标签。
**语法*** 

```html
tableObject.createTFoot()
```

**返回值:**返回新创建的或现有的<元素。

下面的程序说明了 Table createTFoot()方法:
**示例-1:** 创建一个< tfoot >元素。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Table createTFoot() Method in HTML
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
    <h2>Table createTFoot() Method</h2>

<p>To create a footer for a table,
      double-click the "Add Footer" button.</p>

    <table id="Courses" align="center">
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

    <button ondblclick="foot()">
      Add Footer
  </button>

    <script>
        function foot() {
            var MyTable = document.getElementById("Courses");

            // Creating footer.
            var MyFooter = MyTable.createTFoot();
            var MyRow = MyFooter.insertRow(0);
            var MyCell = MyRow.insertCell(0);
            MyCell.innerHTML =
              "<b>Available On GeeksforGeeks.</b>";
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/9551c9725dd8c5bd37dc00588759e1de.png)

**点击按钮后:**

![](img/39e55a33c31861cb40a975a92920fed8.png)

**支持的浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧