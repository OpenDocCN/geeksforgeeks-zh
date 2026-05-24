# CSS 丰富属性

> 原文:[https://www.geeksforgeeks.org/css-richness-property/](https://www.geeksforgeeks.org/css-richness-property/)

**CSS 丰富属性**用于设置将要播放或读取的语句或音频的丰富度或亮度。

**语法:**

```html
richnes: number;
```

**参数:**该属性接受如上所述的单个参数，如下所述:

*   **Number:** This parameter holds an integer value between 0 and 100, which is used for the richness of audio or sentence application.

**示例 1:** 在本例中，我们将在 p 标签的元素上设置丰富度。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        p {
            richness: 75;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>

    <p>CSS richness Property</p>

    <audio controls>
        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3">
    </audio>
</body>

</html>
```