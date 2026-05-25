# jQuery 中 `position()` 和 `offset()` 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-position-and-offset-in-jquery/](https://www.geeksforgeeks.org/what-is-the-difference-between-position-and-offset-in-jquery/)

jQuery UI 方法 `position()` 和 `offset()` 都返回包含 `top` 和 `left` 位置的整数坐标属性的对象。`top` 和 `left` 坐标以像素为单位返回。这两个函数仅适用于可见元素，而不适用于隐藏元素。

## 示例

该示例给出了包含文本的框的 `top` 和 `left` 坐标。

```html
<!DOCTYPE html>
<html>

<head>
    <title>The difference between offset and position Method</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <!-- jQuery code to show the method -->
    <script>
        /* code for position */
        $(document).ready(function() {
            $("#position").click(function() {
                var Geek = $("#testDiv").position();
                alert("Top : " + Geek.top + " Left : " + Geek.left);
            });

            /* code for offset */
            $("#offset").click(function() {
                var Geek = $("#testDiv").offset();
                alert("Top : " + Geek.top + " Left : " + Geek.left);
            });
        });
    </script>

    <style>
        #container {
            width: 40%;
            min-height: 100px;
            padding: 20px;
            font-size: 25px;
            border: 2px solid green;
            font-weight: bold;
            color: green;
            background: gray;
            position: relative;
        }
        #testDiv {
            background: silver;
        }
        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <b>offset() and position()</b>
        <div>
            <div id="container">
                <div id="testDiv">
                  Welcome to GeeksforGeeks
                </div>
            </div>

            <div style="height:10px"></div>
            <button id="offset">click for offset</button>
            <button id="position">click for position</button>
        </div>
    </center>
</body>

</html>
```

## 输出

*   **点击任意按钮前:**
    ![](img/c7e1ad89ac7b95b7c892dae6e9dca592.png)
*   **点击按钮后:**
    ![offset](img/b63d3724b283a93a0d9c3856194e6bbc.png)
    偏移:
    ![position](img/49b326cfcc005f7c46b794efae4f00f5.png)
    位置:

## `offset()` 与 `position()` 方法之差

| `offset()` 方法 | `position()` 方法 |
| :--- | :--- |
| jQuery 中的 `offset()` 方法返回 HTML 元素相对于文档的 `first` 找到的位置。 | jQuery 中的 `position()` 方法返回 HTML 元素相对于其偏移父元素的当前位置。 |
| jQuery UI `offset()` 是相对于文档的。 | jQuery UI `position()` 是相对于父元素的。 |
| 当您想要将新的元素放在另一个已经存在的元素之上时，最好使用 jQuery `offset()` 方法。 | 当您想要在同一个容器中的另一个 DOM 元素附近放置一个新元素时，最好使用 jQuery `position()` 方法。 |
| `offset()` 方法主要用于拖放功能。 | `position()` 方法用于相对于文档、窗口或其他元素（如鼠标或光标）定位元素。 |