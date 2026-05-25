# HTML DOM cite 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-quote-cite-property/](https://www.geeksforgeeks.org/html-dom-quote-cite-property/)

HTML DOM `quote` 元素的 `cite` 属性用于设置或返回引用的 `cite` 属性。`cite` 属性指定引用的源 URL。

## 语法

### 获取引用属性
```html
quoteObject.cite
```

### 设置引用属性
```html
quoteObject.cite = URL
```

## 属性值
包含单值 `URL`，用于指定引用的 URL。该网址的可能值为：

### 绝对 URL
用于指出其他网站（例如 `cite="https://www.geeksforgeeks.org"`）。

### 相对 URL
用于指出网站内的页面（例如 `cite="page.html"`）。

## 返回值
返回代表源文档网址的字符串值。

## 示例 1

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML DOM Quote cite Property
        </title>
    </head>
<body>
        <h1>GeeksforGeeks</h1>
        <h2>DOM Quote cite Property</h2>
        <q id="GFG" cite="geeksforgeeks.org">
            GeeksforGeeks
        </q>
        <br><br>
        <button onclick="Geeks()">
            Submit
        </button>
        <p id="sudo"></p>
        <script>
            function Geeks() {
                var ct = document.getElementById("GFG").cite;
                document.getElementById("sudo").innerHTML = ct;
            }
        </script>
    </body>
</html>
```

**输出：**

*   **点击按钮前：**
    ![](img/3cc4c406363a942981bbca9c62899c0a.png)
*   **点击按钮后：**
    ![](img/100a05b49c91c50af2ec89ba82a42c47.png)

## 示例 2

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML DOM Quote cite Property
        </title>
    </head>
<body>
        <h1>GeeksforGeeks</h1>
        <h2>DOM Quote cite Property</h2>
        <q id="GFG" cite="Finecomb.com">
            GeeksforGeeks
        </q>
        <br><br>
        <button onclick="Geeks()">
            Submit
        </button>
        <p id="sudo"></p>
        <script>
            function Geeks() {
                var ct = document.getElementById("GFG").cite
                         = "www.geeksforgeeks.org";
                document.getElementById("sudo").innerHTML
                         = "The cite was changed to " + ct;
            }
        </script>
    </body>
</html>
```

**输出：**

*   **点击按钮前：**
    ![](img/3cc4c406363a942981bbca9c62899c0a.png)
*   **点击按钮后：**
    ![](img/61490ed1d2b2cb0d27de8338290cb736.png)

## 支持的浏览器
支持的浏览器如下：

*   谷歌 Chrome
*   微软 Edge
*   火狐浏览器
*   苹果 Safari
*   歌剧