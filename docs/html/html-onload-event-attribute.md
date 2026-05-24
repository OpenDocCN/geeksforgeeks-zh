# HTML |加载事件属性

> 原文:[https://www.geeksforgeeks.org/html-onload-event-attribute/](https://www.geeksforgeeks.org/html-onload-event-attribute/)

当一个对象被加载时，这个属性起作用。该属性主要在元素中用于执行脚本。它也可以与其他元素一起使用。此属性用于检查访问者的浏览器类型和浏览器版本，并根据信息加载网页的正确版本。
**支持的标签:**

*   **<体>**
*   **<架>**
*   **<框架集>**
*   **< iframe >**
*   <【img】>
*   **<输入 type="image" >**
*   **<链接>**
*   **<剧本>**
*   **<风格>**

**语法:**

```html
<element onload = "script">
```

**属性值:**该属性包含单值*脚本*，在 onload 事件触发时运行。该属性与许多 HTML 元素相关联。
**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>onload event attribute</title>
        <script>
        function Function() {
            alert("Page is loaded");
        }
        </script>
        <style>
            body {
                text-align:center;
            }
            h1 {
                color:green;
            }
        </style>
    </head>
    <body onload="Function()">
        <h1>GeeksforGeeks</h1>
        <h2>onload event attribute</h2>
    </body>
</html>
```

**输出:**

![](img/fa8bb1bc044b4220a86623ba0fe477ab.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>onload event attribute</title>
    </head>
    <body>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png"
        onload="loadImage()" width="500" height="132">
        <script>
            function loadImage() {
                alert("Image loaded successfully");
            }
        </script>
    </body>
</html>                   
```

**输出:**

![](img/afa524beb372bf74c8e7a216d69e9d59.png)

**支持的浏览器:**加载属性支持的浏览器如下:

*   铬
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧