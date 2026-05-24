# 如何用 HTML 和 CSS 制作玻璃/模糊效果叠加？

> 原文:[https://www . geesforgeks . org/如何制作玻璃-模糊-效果-叠加-使用-html-and-css/](https://www.geeksforgeeks.org/how-to-make-a-glass-blur-effect-overlay-using-html-and-css/)

为了在叠加上产生背景模糊效果，**滤镜:模糊()**属性与**:在**伪元素之前一起使用。“滤镜:模糊()”属性在框或任何需要的元素上产生模糊效果，“之前”用于添加模糊的背景，而不应用任何额外的标记。
**HTML 代码:**在本节中，我们将使用 HTML 代码来设计网页的基本结构。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>
        How to make a CSS glass/blur
        effect work for an overlay?
    </title>

    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>
    <section>
        <div class="layout">
            <h2>GeeksforGeeks</h2>

<p>
                It is a computer science portal for geeks.
                It is a platform where you can learn and
                practice programming problems. It contains
                programming content, web technology content,
                and some other domain content also.
            </p>

            <button class="btn btn-outline-danger">
                Button
            </button>
        </div>
    </section>
</body>

</html>
```

**CSS 代码:**在本节中，我们将使用一些 CSS 属性，使用 HTML 和 CSS 制作一个玻璃/模糊效果叠加。

## 钢性铸铁

```html
<style>
    body {
        margin: 0;
        padding: 0;
    }

    section {
        position: relative;
        background: url(demo.jpg);
        background-attachment: fixed;
        height: 100vh;
    }

    section .layout {
        position: relative;
        top: 35%;
        left: 30%;
        max-width: 600px;
        padding: 50px;
        box-shadow: 0 10px 20px rgba(0, 0, 0, .5);
        color: rgb(255, 254, 254);
    }

    section .layout::before {
        content: '';
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background: url(demo.jpg);
        background-attachment: fixed;
        filter: blur(8px);
    }

    section .layout h2 {
        position: relative;
    }

    section .layout p {
        position: relative;
    }

    section .layout button {
        position: relative;
    }
</style>
```