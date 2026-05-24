# HTML | DOM 列对象

> 原文:[https://www.geeksforgeeks.org/html-dom-column-object/](https://www.geeksforgeeks.org/html-dom-column-object/)

HTML DOM 中的**列对象**用来表示 HTML [<列>](https://www.geeksforgeeks.org/html-col-tag/) 元素。
此标签用于**设置**或**获取 **< col >** 元素的属性。可以使用 **getElementById()** 方法访问。
**语法:**** 

```html
document.getElementById("Col_ID");
```

该列标识被分配给 HTML < col >元素。
**房产价值:**

*   [**跨度**](https://www.geeksforgeeks.org/html-dom-column-span-property/) **:用于设置或返回跨度属性。**

**示例-1:** 使用**文档返回**“col id”**。id；**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Column Object
    </title>
</head>
<style>
    #myCol {
        background: green;
    }

    table {
        color: white;
        margin-left: 150px;
    }

    #Geek_p {
        color: green;
        font-size: 30px;
    }

    td {
        padding: 10px;
    }
</style>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>HTML | DOM Column Object</h2>
    <table>
        <colgroup>
            <col id="myCol" span="2">
                <col style="background-color:green">
        </colgroup>
        <tr>
            <th>S.No</th>
            <th>Title</th>
            <th>Geek_id</th>
        </tr>
        <tr>
            <td>Geek_1</td>
            <td>GeekForGeeks</td>
            <th>Geek_id_1</th>
        </tr>
        <tr>
            <td>Geek_2</td>
            <td>GeeksForGeeks</td>
            <th>Geek_id_2</th>
        </tr>
    </table>
    <br>
    <button onclick="myGeeks()">
        Click
    </button>
    <h4>
            <p id="Geek_p" style="color:green"></p>

        </h4>
    <script>
        function myGeeks() {
            // access col element
            var x = document.getElementById(
                "myCol").id;
            document.getElementById(
                "Geek_p").innerHTML = x;
        }
    </script>
</body>

</html>
```

**输出**T2】

*   **之前点击按钮:**

![](img/b6d73f824fb13fe658c6c9ea5006b035.png)

*   **点击按钮后:**

![](img/57977a5a10b0f42f1d9ee78742174431.png)

**示例-2:** 使用**文档从**“col id”**返回跨度元素的编号。跨度；**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Column Object
    </title>
</head>
<style>
    #myCol {
        background: green;
    }

    table {
        color: white;
        margin-left: 150px;
    }

    #Geek_p {
        color: green;
        font-size: 30px;
    }

    td {
        padding: 10px;
    }
</style>

<body style="text-align:center;">

    <h1 style="color:green;">
            GeeksForGeeks
        </h1>

    <h2>HTML | DOM Column Object</h2>
    <table>
        <colgroup>
            <col id="myCol" span="2">
                <col style="background-color:green">
        </colgroup>
        <tr>
            <th>S.No</th>
            <th>Title</th>
            <th>Geek_id</th>
        </tr>
        <tr>
            <td>Geek_1</td>
            <td>GeekForGeeks</td>
            <th>Geek_id_1</th>
        </tr>
        <tr>
            <td>Geek_2</td>
            <td>GeeksForGeeks</td>
            <th>Geek_id_2</th>
        </tr>
    </table>
    <br>
    <button onclick="myGeeks()">
        Click
    </button>
    <h4>
            <p id="Geek_p" style="color:green"></p>

        </h4>
    <script>
        function myGeeks() {
            // access col element
            var x = document.getElementById(
                "myCol").span;
            document.getElementById(
                "Geek_p").innerHTML = x;
        }
    </script>
</body>

</html>
```

**输出**T2】

*   **之前点击按钮:**

![](img/b6d73f824fb13fe658c6c9ea5006b035.png)

*   **点击按钮后:**

![](img/509d11831964ef17ad515bedc57bc580.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Mozilla Firefox
*   边缘
*   旅行队
*   歌剧