# CSS 提升属性

> 原文:[https://www.geeksforgeeks.org/css-elevation-property/](https://www.geeksforgeeks.org/css-elevation-property/)

**CSS elevation 属性**用于根据听者的环境将声源设置在垂直轴上。

**语法:**

```html
elevation: angle:

```

**参数:**该属性接受如上所述的单个值，如下所述:

*   **Angle:** This parameter stores the angle of the sound source that produces sound. Within the range of 90 degrees to -90 degrees, this parameter accepts few possible values. Job title is acceptable.

```html
above = 90deg
level = 0deg
below = -90deg
higher = shifted upwards by 10deg compare to initial(0deg)
lower = shifted downwards by 10deg compare to initial(0deg)

```

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        audio {
            elevation: above;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>

    <p>CSS elevation Property</p>

    <audio controls>
        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3">
    </audio>
</body>

</html>
```