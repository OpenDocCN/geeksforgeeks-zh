# HTML DOM 表格属性

> 原文：[https://www.geeksforgeeks.org/html-dom-table-thead-property/](https://www.geeksforgeeks.org/html-dom-table-thead-property/)

`table`属性用于返回对表格的`<thead>`元素的引用。
`<thead>`元素用于将HTML表格中的标题内容分组。
如果`<thead>`元素未定义，则返回`null`。

**语法**

```html
tableObject.tHead
```

**返回值：** 对表中`<thead>`元素的引用，如果没有定义则为`null`。

下面的程序说明了`Table tHead()`属性：

### 示例

提醒`<thead>`元素的内部HTML。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Table tHead Property in HTML</title>
    <style>
        table, td {
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
    <h2>Table tHead Property</h2>
    <p>To return the innerHTML of the thead element for the table, double-click the "Return Header" button.</p>
    <table id="Courses" align="center">
        <thead>
            <tr>
                <th>Subject</th>
                <th>Courses</th>
            </tr>
        </thead>
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
    <button ondblclick="thead()">Return Header</button>
    <script>
        function thead() {
            // returning reference of tHead using alert.
            alert(document.getElementById("Courses").tHead.innerHTML);
        }
    </script>
</body>
</html>
```

**输出：**

**点击按钮前：**

![](img/9504c86d6f82305e439c4b03ae7abeb0.png)

**点击按钮后：**

![](img/150ad6f884c7ebb3330b83a349fefeaa.png)

**支持的浏览器：**

*   Apple Safari
*   Microsoft Edge
*   Firefox
*   Google Chrome
*   Opera