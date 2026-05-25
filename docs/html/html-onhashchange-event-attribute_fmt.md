
# HTML | on hashchange 事件属性

> 原文: [https://www.geeksforgeeks.org/html-onhashchange-event-attribute/](https://www.geeksforgeeks.org/html-onhashchange-event-attribute/)

当锚定部分发生变化时，此属性起作用。锚点部分以当前网址的“#”符号开始。

## 支持的标签

*   **<body>**

## 语法

```html
<element onhashchange="script">
```

## 属性值

该属性包含单值脚本，在 onhashchange 事件属性触发时运行。该属性仅与 `<body>` 标签相关联。

## 示例

```html
<!DOCTYPE html>
<html>
    <head>
        <title>onhashchange event attribute</title>
        <style>
            body {
                text-align:center;
            }
            h1 {
                color:green;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>onhashchange event attribute</h2>
        <button onclick="changePart()">Try it</button>
        <div id="gfg"></div>
        <script>
        function changePart() {
            location.hash = "2";
            var geeks = "Anchor part: " + location.hash;
            document.getElementById("gfg").innerHTML = geeks;
        }
        function myFunction() {
            alert("The anchor part has changed!");
        }
        </script>
</html>
```

## 输出

![输出](img/d0305dfb75efba246963124f1a2d3774.png)

## 支持的浏览器

事件属性支持的浏览器如下：

*   Chrome 5.0
*   Internet Explorer 8.0
*   Firefox 3.6
*   Safari 5.0
*   Opera 10.6
