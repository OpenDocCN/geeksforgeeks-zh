# HTML |窗口顶部( )属性

> 原文:[https://www.geeksforgeeks.org/html-window-top-property/](https://www.geeksforgeeks.org/html-window-top-property/)

**窗口顶端()属性**用于返回当前窗口最顶端的浏览器窗口。它是一个只读属性，并返回对窗口层次结构中最顶层窗口的引用。
**语法:**

```html
window.top
```

**返回值:**返回窗口层次结构中最顶层窗口的引用。

下面的程序说明了 Window top()属性:
**检查窗口是否是最顶端的浏览器窗口。**T3】

## 超文本标记语言

```html
<!DOCTYPE>
<html>

<head>
    <title>
      Window top() property in HTML
    </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Window top() Property</h2>

<p>
      For checking whether the window is the
      topmost window or not, double click the
      "Check Top Window" button:
    </p>

    <button ondblclick="Window()">
      Check Top Window
    </button>

    <p id="MyWindow"></p>

    <script>
        function Window() {
            if (window.top = window.self) {
                document.getElementById("MyWindow").innerHTML =
                    "This window is the topmost window.";
            } else {
                document.getElementById("demo").innerHTML =
                    "This window is not the topmost window.";
            }
        }
    </script>
</body>

</html>
```

**输出:**

![](img/7e2bd431de2f09de3c275b13362cbe52.png)

**点击**按钮后

![](img/62cd7878cd38bf84408a4b7e7b886189.png)

**支持的浏览器:***窗口顶部( )属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队