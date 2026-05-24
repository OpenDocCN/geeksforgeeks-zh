# CSS 音高范围属性

> 原文:[https://www.geeksforgeeks.org/css-pitch-range-property/](https://www.geeksforgeeks.org/css-pitch-range-property/)

CSS 音高范围属性用于设置声音的频率范围。会有一个限制，这样用户就不会有任何听力问题。

**语法:**

```html
pitch-range: number;
```

**参数:**该属性接受如上所述的单个参数，如下所述:

*   **No.:** The frequency number stored in this parameter can be in the range of 0-100.

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        audio {
            pitch-range: 75;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>

    <p>CSS pitch-range Property</p>

    <audio controls>
        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3">
    </audio>
</body>

</html>
```