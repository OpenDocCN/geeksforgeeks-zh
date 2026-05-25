# 如何使用 HTML 同时更新两帧？

> 原文: [https://www.geeksforgeeks.org/how-to-update-two-frames-at-the-same-time-using-html/](https://www.geeksforgeeks.org/how-to-update-two-frames-at-the-same-time-using-html/)

我们将看看你如何能同时更新两帧。

**方法:** 我们采用两个具有唯一 id 名称的 `iframe`，即 `frame1` 和 `frame2`，都与页面中心和一个按钮对齐。当我们点击按钮时，`iframe` 的 URL 会被其他 URL 替换。

## HTML 代码

在这段代码中，我们在按钮上附加了一个 `addEventListener`。当我们点击按钮时，应该使用两个 `iframe` 的 `src` 属性，一次同时将正文内容更改为两个 `iframe` 的 URL。

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="display:flex;
        justify-content:center;color:green;">
        GeeksforGeeks
    </h1>

<div style="padding:10px;border:2px solid green;">

<div style="display:flex;flex-wrap:wrap;
            justify-content:center;">
            <iframe src=
"https://www.youtube.com/embed/aMn7sO1d4Yc" id="frame1">
            </iframe>
            <div style="width:10px;">
            </div>
            <iframe src=
"https://www.youtube.com/embed/8Pv96bvBJL4" id="frame2">
            </iframe>
        </div>
        <button style="margin-left:50%;margin-right:30%;
            margin-top:10px;" id="update">
            Click me
        </button>
    </div>

<script>
        document.getElementById('update')
            .addEventListener('click', function () {

// Change src attribute of iframes at a same time
            document.getElementById('frame1').src =
                'https://www.youtube.com/embed/QS8xU4TqnQE';
            document.getElementById('frame2').src =
                'https://www.youtube.com/embed/3w0XfBU2ufw';
        });
    </script>
</body>

</html>
```

## 输出

![](img/ca2a1784ee069f9919e5020ffde7c607.png)

输出

**注意:** 我们可以用 `<a>` 标签的 `target` 属性来更新框架内容。我们想要在 `iframe` 中打开的 URL 将替换之前存在的 `iframe` 的 URL。我们点击“*click me*”链接，将“b.html”替换为“a.html”。