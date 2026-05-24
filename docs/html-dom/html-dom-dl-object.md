# HTML | DOM dl 对象

> 原文:[https://www.geeksforgeeks.org/html-dom-dl-object/](https://www.geeksforgeeks.org/html-dom-dl-object/)

**DOM dl 对象**用于表示 HTML < dl >元素。可以使用 **getElementById()** 方法访问 dl 元素。 **dl** 用于创建一个 HTML 格式的描述列表。

**语法:**

```html
document.getElementById("id"); 
```

其中‘id’是分配给 **dl** 标签的 ID。

**示例-1:** 在下面的程序中，dl 元素被访问，并且描述列表中文本的颜色被改变。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<body>
        <h1 style = "color:green;" >
          GeeksForGeeks
        </h1>
        <h2>DOM dl Object</h2>

        <dl id="id">
          <dt>Sorting</dt>
          <dd>Merge sort</dd>
        </dl>

        <button onclick="Geeks()">Click Here!</button>

        <p id="p" style="color:green"></p>

        <script>
        function Geeks() {
          var doc = document.getElementById("id").innerHTML;

          document.getElementById("p").innerHTML = doc;
        }
        </script>
</body>
</html>
```

**输出:**
**点击按钮前:**

![dl](img/9f10453698554217b918d0d4f7d10141.png)

**点击按钮后:**

![dl](img/e9790aa5faebf5ea791ea33bdf35db53.png)

**示例-2:** 可以使用**文档.创建元素**方法创建 DL 对象。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<body>
        <h1 style = "color:green;" >
          GeeksForGeeks
        </h1>
        <h2>DOM dl Object</h2>

        <button onclick="Geeks()">Click Here!</button><br>
        <script>
        function Geeks() {
          // Creating a dl element
          var doc = document.createElement("DL");
          doc.setAttribute("id", "dl");
          document.body.appendChild(doc);

          // Creating a DT element
          var doc1 = document.createElement("DT");
          var txt1 = document.createTextNode("Sorting");
          doc1.appendChild(txt1);
          doc1.setAttribute("id", "dt");
          document.getElementById("dl").appendChild(doc1);

          // Creaiting a dd element
          var doc2 = document.createElement("DD");
          var txt2 = document.createTextNode("Merge sort");
          doc2.appendChild(txt2);
          document.getElementById("dl").appendChild(doc2);
        }
        </script>
</body>
</html>
```

**输出:**
**点击按钮前:**

![dl](img/11177c4c2b9f417279de3d87c6a7edcc.png)

**点击按钮后:**

![dl](img/474f4dc105474c379ee45dac22dcdde8.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Mozilla Firefox
*   边缘
*   旅行队
*   歌剧