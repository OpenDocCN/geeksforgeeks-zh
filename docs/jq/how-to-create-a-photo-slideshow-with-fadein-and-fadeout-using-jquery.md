# 如何使用 jQuery 创建 fadeIn 和 fadeOut 的照片幻灯片？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-create-a-photo-slideshow-with-fadein-and-fadeout-using-jquery/) 创建带有渐进渐出的照片幻灯片显示

在本文中，我们将使用 jQuery[**【fade in()】**](https://www.geeksforgeeks.org/jquery-fadein-method/)和 [**fadeOut()**](https://www.geeksforgeeks.org/jquery-effect-fadeout-method/) 功能创建一个简单的幻灯片显示。

**进场:**

*   对于所有图像的幻灯片显示效果，我们将使用 JavaScript [**设置间隔()**](https://www.geeksforgeeks.org/java-script-settimeout-setinterval-method/) 功能。此函数以指定的时间间隔调用函数或计算表达式，该时间间隔以毫秒为单位。
*   **fadeIn():** 此方法逐渐增加所选元素的不透明度，即由隐藏变为可见。
*   **淡出():**此方法用于淡出特定元素。

**示例:**在下面的代码中，我们正在用幻灯片显示的第一个图像创建一个 HTML [*< div >*](https://www.geeksforgeeks.org/div-tag-html/) 元素。接下来，我们将添加 CSS 来设置幻灯片的样式。然后，我们将 jQuery 库加载到我们的脚本中。

我们正在使用一个数组来存储幻灯片的所有图像。我们正在使用带有 *fadeIn()* 和 *fadeOut()* 的*设置间隔()*功能。我们正在使用 [*attr()*](https://www.geeksforgeeks.org/jquery-attr-method/) 方法来更改图像源。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
        "https://code.jquery.com/jquery-3.4.1.min.js">
    </script>

    <style>
        .slideshow {
            margin: auto;
            width: 60%;
            border: 3px solid #73ad21;
            padding: 10px;
        }

        .slideshow img {
            width: 100%;
            height: 100%;
        }
    </style>

    <script>
        $(document).ready(function () {
            var pic = $("img:first");
            var images = [
"https://media.geeksforgeeks.org/wp-content/uploads/20210629182827/img1.jpg",
"https://media.geeksforgeeks.org/wp-content/uploads/20210629182923/img2.jpg",
"https://media.geeksforgeeks.org/wp-content/uploads/20210629182952/img3.jpg",
"https://media.geeksforgeeks.org/wp-content/uploads/20210629183022/img4.jpg",
            ];

            var i = 0;
            setInterval(function () {

                // Returns 0, 1, 2, 3, 0, 1, 2, ....
                i = (i + 1) % images.length;
                pic.fadeOut(250, function () {
                    $(this).attr("src", images[i]);
                    $(this).fadeIn(1050);
                });
            }, 5000);
        });
    </script>
</head>

<body>
    <div class="slideshow">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210629182827/img1.jpg" />
    </div>
</body>

</html>
```

**输出:**

![](img/87f541c3623a908c62b4a4c14df0764d.png)