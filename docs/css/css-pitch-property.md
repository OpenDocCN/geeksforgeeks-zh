# CSS 间距属性

> 原文:[https://www.geeksforgeeks.org/css-pitch-property/](https://www.geeksforgeeks.org/css-pitch-property/)

CSS 音高属性用于定义声音的频率。每一个产生不同频率的声音。改变任何声音的频率都会对听者产生不同的影响。

**语法:**

```html
pitch: frequency;
```

**属性值:**该属性接受如上所述的单个值，如下所述:

*   **Frequency:** This attribute value holds the value of frequency. Possible values are X high, high, medium, low and X low.

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        audio {
            pitch: x-high;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <p>CSS pitch Property</p>

    <audio controls>
        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
            type="audio/mp3">
    </audio>
</body>

</html>
```