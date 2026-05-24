# HTML | DOM 引用对象

> 原文:[https://www.geeksforgeeks.org/html-dom-cite-object/](https://www.geeksforgeeks.org/html-dom-cite-object/)

**DOM 引用对象**用于表示 [HTML <引用>元素](https://www.geeksforgeeks.org/html-cite-tag/)。引用元素由**获取元素 ById()** 访问。
**语法**

```html
document.getElementById("id");
```

其中“id”是分配给**引用**标签的 ID。
**示例-1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM cite Object</title>
    <style>
        body {
            text-align: center;
        }
    </style>
</head>

<body>
    <img src="https://media.geeksforgeeks.org
              /wp-content/uploads/geeksforgeeks-25.png"
         alt="gfg">

    <!-- cite id-->

<p><cite id="GFG">GeeksforGeeks Image</cite></p>

    <button onclick="Geeks()">Submit</button>

    <script>
        function Geeks() {
            var w = document.getElementById("GFG");
            w.style.color = "coral";
            w.style.fontWeight = "bold";
        }
    </script>
</body>

</html>            
```

**输出:**
**点击按钮前:**

![](img/1aca167f03295fc0c25a8143fd6a4019.png)

**点击按钮后:**

![](img/bbe36cf240b795995a5f7539466f38ff.png)

**示例-2:** 引用对象可以使用**文档.创建元素**方法创建。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM cite Object</title>
    <style>
        body {
            text-align: center;
        }
    </style>
</head>

<body>
    <h2>DOM Cite Object</h2>

    <button onclick="Geeks()">
      Submit
    </button>

    <img src="https://media.geeksforgeeks.org
              /wp-content/uploads/geeksforgeeks-25.png"
         alt="gfg">

    <script>
        function Geeks() {
            var cite = document.createElement("CITE");

            var text =
            document.createTextNode("GeeksforGeeks Image");

            cite.appendChild(text);
            document.body.appendChild(cite);
        }
    </script>
</body>

</html>                   
```

**输出**
**点击按钮前:**

![](img/88cf34ec9b598eb203eee6b0b358fc66.png)

**点击按钮后:**

![](img/99dc4a7b75e0f5bce11665b7d45aacb6.png)

**支持的浏览器:****DOM Cite Object**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队