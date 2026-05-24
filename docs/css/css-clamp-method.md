# CSS 夹钳()方法

> 原文:[https://www.geeksforgeeks.org/css-clamp-method/](https://www.geeksforgeeks.org/css-clamp-method/)

clamp()方法用于将值限制在上限和下限之间。它需要以下列出的三个参数:

*   最小值
*   基准价值
*   最大值

当首选值小于最小值时，最小值会派上用场。同样，当首选值大于最大值时，最大值也会派上用场。首选值在最小值和最大值之间时变得有用。

clamp()函数可用于各种元素，如字体大小、宽度等。让我们构建一个简单的布局来清楚地了解 clamp()函数

**语法:**

```html
clamp(value1, value2, value3)
```

**参数:**

*   这里，值 1 代表最小值，值 2 代表首选值，值 3 代表最大值。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>

        /* Setting clamp property of heading */
        h1 {
            font-size: clamp(2rem, 4vw, 4rem);
            color: #eb4034;
        }

        /* Setting clamp property of box */
        .box {
            width: clamp(150px, 50%, 400px);
            height: 8rem;
            background: #5f76e8;
        }
    </style>
</head>

<body>
    <div class="container">
        <h1>Welcome To GFG</h1>
        <div class="box"></div>
    </div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-493706-1" width="640" height="360" loop="1" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200928232126/GFG.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200928232126/GFG.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200928232126/GFG.mp4)</video>

在上面显示的示例中，我们看到了在夹钳功能的帮助下，根据视口调整宽度和字体大小是多么容易。clamp()函数对于排版和创建流体布局非常有用。

**支持的浏览器:**

*   铬
*   歌剧
*   旅行队
*   火狐浏览器
*   边缘