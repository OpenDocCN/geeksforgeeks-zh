# HTML DOM 图片 alt 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-image-alt-property/](https://www.geeksforgeeks.org/html-dom-image-alt-property/)

[**HTML**](https://www.geeksforgeeks.org/html-tutorials/)**DOM Image[alt](https://www.geeksforgeeks.org/html-alt-attribute/#:~:text=The%20HTML%20alt%20attribute%20is,the%20value%20assigned%20to%20it.)属性用于设置或返回图像元素的 **alt** 属性的值。 **alt** 属性用于指定图像的替代文本。当图像不显示时，它很有用。它用于为图像提供替代信息。**

****语法:****

**它返回图像 alt 属性**

```html
ImageObject.alt
```

**它设置图像替代属性。**

```html
ImageObject.alt = text
```

****属性值:**它包含一个指定图像替代文本的值。**

****返回值:**返回一个字符串值，代表图像的替换文本。**

****示例 1:** 本示例返回图像 alt 属性。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h2>HTML DOM Image alt Property</h2>

        <img id="GFG" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190506164011/logo3.png"
            alt="GeeksforGeeks logo" />
        <br />

        <button onclick="Geeks()">Click me!</button>

        <p id="sudo"></p>
    </center>

    <script>
        function Geeks() {
            var g = document.getElementById("GFG").alt;
            document.getElementById("sudo").innerHTML = g;
        }
    </script>
</body>

</html>
```

****输出:****

**![image alt](img/94c6bcbde59d7e06ddf6270e74572a68.png)**

****示例 2:** 本示例设置图像 alt 属性。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h2>HTML DOM Image alt Property</h2>

        <img id="GFG" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190506164011/logo3.png"
            alt="GeeksforGeeks logo" />
        <br />

        <button onclick="Geeks()">
            Click me!
        </button>

        <p id="sudo"></p>
    </center>

    <script>
        function Geeks() {
            var g = (document.getElementById("GFG").alt
                = "Hello GeeksForGeeks");

            document.getElementById("sudo").innerHTML = g;
        }
    </script>
</body>

</html>
```

****输出:****

**![](img/21978f3eb9b0a3095e8adcad333b5f0b.png)**