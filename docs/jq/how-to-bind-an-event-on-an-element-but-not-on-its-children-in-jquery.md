# 如何在 jQuery 中将一个事件绑定在一个元素上，而不绑定在其子元素上？

> 原文:[https://www . geeksforgeeks . org/如何绑定元素上的事件但不绑定其 jquery 中的子代/](https://www.geeksforgeeks.org/how-to-bind-an-event-on-an-element-but-not-on-its-children-in-jquery/)

在本文中，我们将学习如何在 jQuery 中将事件绑定到元素上，而不是其子元素上。我们希望在父元素上而不是子元素上添加一个事件。

**进场:**我们可以按照以下步骤完成这项任务:

*   首先，我们使用 JQuery 中的[**(on)**](https://www.geeksforgeeks.org/jquery-on-with-examples/)函数在包含段落元素的 div 元素上添加一个点击事件。
*   然后为了使 click 事件只在父元素上可用，我们调用一个函数来检查被单击的元素是否是父元素。如果是父级，我们调用 alert()函数。否则，我们什么都不做。
*   该函数如下所示:

```html
$('.parent').on('click', function(e) {
    if (e.target == this){
        alert( 'clicked on parent element' );
    }
});
```

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>

    <style>
        body {
            color: green;
            font-size: 30px;
        }

        div {
            font-size: 40px;
        }

        button {
            font-size: 30px;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <div class='parent'>
            click to see changes(parent)
            <p style="color: red;" class="child">
                This will not work(Child)
            </p>
        </div>
    </center>

    <script>
        $('.parent').on('click', function (e) {
            if (e.target == this) {
                alert('clicked on parent element');
            }
        });
    </script>
</body>

</html>
```

输出:

<video class="wp-video-shortcode" id="video-621732-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210527172836/bandicam-2021-05-27-17-26-32-026.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210527172836/bandicam-2021-05-27-17-26-32-026.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210527172836/bandicam-2021-05-27-17-26-32-026.mp4)</video>

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>

    <style>
        body {
            color: green;
            font-size: 30px;
        }

        div {
            font-size: 40px;
        }

        button {
            font-size: 30px;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <ul>
        <li style="color: red;" class='parent'>
            click to see changes(parent)
        </li>
        <ul>
            <li class="child">This will not work(child)</li>
            <ul>
                <li>This will also not work (GrandChild)</li>
            </ul>
        </ul>
    </ul>

    <script>
        $('.parent').on('click', function (e) {
            if (e.target == this) {
                alert('clicked on parent element');
            }
        });
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-621732-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210611194100/bandicam-2021-06-11-19-39-34-052.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210611194100/bandicam-2021-06-11-19-39-34-052.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210611194100/bandicam-2021-06-11-19-39-34-052.mp4)</video>