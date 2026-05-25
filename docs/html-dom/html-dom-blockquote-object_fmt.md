# HTML DOM Blockquote 对象

> 原文：[https://www.geeksforgeeks.org/html-dom-blockquote-object/](https://www.geeksforgeeks.org/html-dom-blockquote-object/)

`DOM 块引用对象`用于表示 HTML `<blockquote>` 元素。`getElementById()` 访问 Blockquote 元素。

## 语法

```html
document.getElementById("id");
```

其中 `"id"` 是分配给 `<blockquote>` 标签的 ID。

## 属性

*   `cite`：用于设置或返回引用的 cite 属性的值。

## 示例-1

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM blockquote object</title>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2> DOM <blockquote> Object</h2>
    <blockquote id="GFG" cite="www.geeksforgeeks.org">
      GeeksforGeeks: A computer science portal for geeks
    </blockquote>

    <button onclick="myGeeks()">Submit</button>

    <p id="sudo"></p>

    <script>
        function myGeeks() {
            var w = document.getElementById("GFG").cite;
            document.getElementById("sudo").innerHTML = w;
        }
    </script>
</body>

</html>
```

**输出：**

**点击按钮前：**

![](img/f9f0d2449f70f43d684adae327bc8c85.png)

**点击按钮后：**

![](img/79966cd8457b8c18aead369e1de5a3d2.png)

## 示例-2

可以使用 `document.createElement` 方法创建区块引用对象。

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM blockquote object</title>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2> DOM <blockquote> Object</h2>

    <button onclick="myGeeks()">Submit</button>

    <p id="sudo"></p>

    <script>
        function myGeeks() {
            var g = document.createElement("BLOCKQUOTE");
            var f = document.createTextNode("GeeksforGeeks:"+
                "A computer science portal for geeks.");

            g.setAttribute("cite", "www.geeksforgeeks.org");
            g.appendChild(f);
            document.body.appendChild(g);
        }
    </script>
</body>

</html>
```

**输出：**

**点击按钮前：**

![](img/bfd789f26300756460c1cb675dbdc5b2.png)

**点击按钮后：**

![](img/6f084120c34d8c21fba05528f0a6eb93.png)

## 支持的浏览器

`DOM blockquote` 对象支持的浏览器如下：

*   谷歌 Chrome
*   微软 Edge
*   火狐浏览器
*   Opera
*   Safari