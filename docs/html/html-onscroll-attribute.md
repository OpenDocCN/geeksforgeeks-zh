# HTML |整体属性

> 原文:[https://www.geeksforgeeks.org/html-onscroll-attribute/](https://www.geeksforgeeks.org/html-onscroll-attribute/)

当滚动元素滚动条时，onscroll 属性起作用。若要在元素中创建滚动条，请使用 CSS 溢出属性。
**支持的标签:**支持所有 HTML 元素。

**语法:**

```html
<element onscroll = "script">
```

**属性:**所有 HTML 元素都支持该属性，脚本触发时该属性工作。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>onscroll attribute</title>
    <style>
        #gfg {
            border: 1px solid black;
            width: 400px;
            height: 100px;
            overflow: scroll;
            text-align: justify;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>onscroll attribute</h2>

    <div id="gfg" onscroll="Geeks()">
      <b>GeeksforGeeks:</b> A computer science portal for
      geeks.It ia a good wqebsite for learning computer
      science. It has a good programming Question and have
      many Interwiew Experiences. Prepare for the Recruitment
      drive of product based companies like Microsoft,
      Amazon, Adobe etc with a free online placement
      preparation course. The course focuses on various
      MCQ's & Coding question likely to be asked in the
      interviews & make your upcoming placement season
      efficient and successful.
    </div>
    <script>
        function Geeks() {
            document.getElementById("gfg").style.color = "green";
        }
    </script>

</body>

</html>
```

**输出:**

![](img/fda70cdeeabb41ff25ce262f230ec13a.png)

**支持的浏览器:**由 *onscroll* 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队