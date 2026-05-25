# HTML DOM Area hostname 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-area-hostname-property/](https://www.geeksforgeeks.org/html-dom-area-hostname-property/)

HTML 中的 `area` 元素的 `hostname` 属性用于返回当前 URL 的主机名。`hostname` 属性返回一个字符串，该字符串包含域名或 URL 的 IP 地址。

## 语法

- 它返回 `area` 元素的 `hostname` 属性。

```html
areaObject.hostname
```

- 它用于设置 `area` 元素的 `hostname` 属性。

```html
areaObject.hostname = hostname
```

## 属性值

它包含单个值 `hostname`，用于指定 URL 的主机名。

## 返回值

返回一个代表 URL 域名的字符串值。

## 示例 1

本示例返回 `area` 元素的 `hostname` 属性。

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML DOM Area hostname Property</title>
</head>
<body>
    <h4>HTML DOM Area hostname Property</h4>
    <button onclick="GFG()">Click Here!</button>
    <map name="Geeks1">
        <area id="Geeks"
              shape="rect"
              coords="0, 0, 110, 100"
              alt="Geeks"
              href="https://manaschhabra:manaschhabra499@www.geeksforgeeks.org:80/"
              target="_self">
    </map>

    <img src="https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
         width="300"
         height="100"
         alt="Geeksforgeeks"
         usemap="#Geeks1">
    <br>
    <p id="GEEK!"></p>

    <script>
        function GFG() {
            // Return hostname property.
            var x = document.getElementById("Geeks").hostname;
            document.getElementById("GEEK!").innerHTML = x;
        }
    </script>
</body>
</html>
```

**输出：**
点击按钮前：
![](img/fa4886e19ef7110ea106ec5fff4e49fe.png)

点击按钮后：
![](img/24457f9aab36f3890593d83a106eabba.png)

## 示例 2

本示例设置 `area` 元素的 `hostname` 属性。

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML DOM Area hostname Property</title>
</head>
<body>
    <h4>HTML DOM Area hostname Property</h4>
    <button onclick="GFG()">Click Here!</button>
    <map name="Geeks1">
        <area id="Geeks"
              shape="rect"
              coords="0, 0, 110, 100"
              alt="Geeks"
              href="https://manaschhabra:manaschhabra499@www.geeksforgeeks.org:80/"
              target="_self">
    </map>

    <img src="https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
         width="300"
         height="100"
         alt="Geeksforgeeks"
         usemap="#Geeks1">
    <br>
    <p id="GEEK!"></p>

    <script>
        function GFG() {
            // Set hostname property.
            var x = document.getElementById("Geeks").hostname = "ide.geeksforgeeks.org";
            document.getElementById("GEEK!").innerHTML = "The hostname has been changed to " + x;
        }
    </script>
</body>
</html>
```

**输出：**
点击按钮前：
![](img/fa4886e19ef7110ea106ec5fff4e49fe.png)

点击按钮后：
![](img/b328a9b46590c06ad5c7fad39b0ad3c5.png)

## 支持的浏览器

- 谷歌 Chrome
- 火狐浏览器
- 微软公司出品的 web 浏览器
- 歌剧
- 旅行队