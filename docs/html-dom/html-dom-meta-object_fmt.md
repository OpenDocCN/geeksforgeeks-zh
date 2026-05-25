# HTML DOM Meta 对象

> 原文: [https://www.geeksforgeeks.org/html-dom-meta-object/](https://www.geeksforgeeks.org/html-dom-meta-object/)

**DOM Meta 对象**用于表示 HTML [`<meta>`](https://www.geeksforgeeks.org/?p=224850) 元素。Meta 元素通过 `document.getElementById()` 获取。

## 属性

*   [`name` 属性](https://www.geeksforgeeks.org/html-dom-meta-name-property/?ref=rp): 此属性用于定义属性名称。
*   [`http-equiv` 属性](https://www.geeksforgeeks.org/html-dom-meta-httpequiv-property/?ref=rp): 该属性用于获取 http 响应消息头。
*   `scheme` 属性: 该属性用于指定解释属性值的方案。
*   [`content` 属性](https://www.geeksforgeeks.org/html-dom-meta-content-property/?ref=rp): 该属性用于指定属性值。

## 语法

```html
document.getElementById("ID");
```

其中 `"id"` 是分配给 `"meta"` 标签的 ID。

## 例-1

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="keywords"
          content="Meta Tags, Metadata" />
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <h2>DOM Meta Object</h2>

        <p>Hello GeeksforGeeks!</p>

        <button onclick="myGeeks()">
            Submit</button>

        <p id="sudo"></p>

        <script>
            function myGeeks() {
                var x = document.getElementsByTagName("META")[0].content;
                document.getElementById("sudo").innerHTML = x;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**

**点击按钮前:**

![](img/fcd4a0b76e928b6af92f62ed3d8338dc.png)

**点击按钮后:**

![](img/d42df08d6c21c8e7158581dc6793dc0c.png)

## 示例-2

可以使用 `document.createElement()` 方法创建 Meta 对象。

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM Meta Object </title>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <h2>DOM Meta Object</h2>

        <p>Hello GeeksforGeeks!</p>

        <button onclick="myGeeks()">
            Submit</button>

        <p id="sudo"></p>

        <script>
            function myGeeks() {
                // meta tag created
                var g = document.createElement("META");
                g.setAttribute("name", "keywords");
                g.setAttribute("content", "Meta Tags, Meta data");
                document.head.appendChild(g);
                document.getElementById("sudo").innerHTML = "HTML DOM Meta Object created.";
            }
        </script>
    </center>
</body>

</html>
```

**输出:**

**点击按钮前:**

![](img/fcd4a0b76e928b6af92f62ed3d8338dc.png)

**点击按钮后:**

![](img/c18ec1070bf1afba617ef6397da39dde.png)

## 支持的浏览器

**DOM Meta 对象**支持的浏览器如下:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Opera
*   Safari