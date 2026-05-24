# HTML DOM 图像宽度属性

> 原文:[https://www . geesforgeks . org/html-DOM-image-width-property/](https://www.geeksforgeeks.org/html-dom-image-width-property/)

[**HTML**](https://www.geeksforgeeks.org/html-tutorials/)**DOM Image width Property**用于设置或返回[**<img>**](https://www.geeksforgeeks.org/html-img-tag/)**元素的 **width** 属性的值。它以像素为单位返回一个数值。**

****语法:****

**它返回 width 属性。**

```html
imageObject.width
```

**它设置宽度属性。**

```html
imageObject.width = pixels
```

****属性值:****

*   ****像素:**以像素为单位指定图像元素的宽度。**

****返回值:**返回一个字符串值，以像素为单位表示图像的宽度。**

****示例 1:** 本示例说明如何返回图像宽度属性。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <h2>HTML DOM Image width Property</h2>

        <img id="GFG" src=
"https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
            width="400" height="150" />
        <br>

        <button onclick="Geeks()">
            Click me!
        </button>

        <p id="sudo"></p>

    </center>

    <script>
        function Geeks() {
            var g = document.getElementById("GFG").width;
            document.getElementById("sudo").innerHTML = g + "px";
        }
    </script>
</body>

</html>
```

****输出:****

**![](img/c0f62af7d44a26984734c2b6c9dcf8ee.png)**

****示例 2:** 本示例设置图像宽度属性。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <h2>HTML DOM Image width Property</h2>

        <img id="GFG" src=
"https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
            width="400" height="150" />
        <br>

        <button onclick="Geeks()">
            Click me!
        </button>

        <p id="sudo"></p>

    </center>
    <script>
        function Geeks() {
            var g = document.getElementById("GFG").width = "200";
            document.getElementById("sudo").innerHTML = g + "px";
        }
    </script>
</body>

</html>
```

****输出:****

**![](img/5bb74f1088143006e62f308c2d3a0b33.png)**

****支持的浏览器:****

*   **谷歌 Chrome**
*   **微软公司出品的 web 浏览器**
*   **火狐浏览器**
*   **苹果 Safari**
*   **歌剧**