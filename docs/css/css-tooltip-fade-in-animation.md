# CSS |工具提示淡入动画

> 原文:[https://www . geesforgeks . org/CSS-tooltip-淡入动画/](https://www.geeksforgeeks.org/css-tooltip-fade-in-animation/)

当鼠标悬停在某个元素上时，工具提示用于显示该元素的相关信息。默认情况下，工具提示显示没有延迟(动画)。

**如何给 Tooltip 添加动画？**
我们可以在工具提示文本变得可见之前为其添加淡入效果。这可以通过使用 CSS 中的**过渡**属性在给定的秒数内将**不透明度**从 0 更改为全。

**语法:**

```html
 .tooltip .tooltip_text {
      opacity: 0;
      transition: opacity 3s;
 }

 .tooltip:hover .tooltip_text {
      visibility: visible;
      opacity: 1;
 }

```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .tooltip {
            position: relative;
            display: inline-block;
            color: green;
            font-size: 30px;
        }

        .tooltip .tooltip_text {
            visibility: hidden;
            font-size: 15px;
            padding: 5px;
            background-color: #cceabb;
            color: black;
            text-align: center;
            position: absolute;
            z-index: 1;
            top: 120%;
            left: 5%;
            opacity: 0;
            transition: opacity 3s;
        }

        .tooltip .tooltip_text::after {
            content: "";
            position: absolute;
            bottom: 100%;
            left: 50%;
            margin-left: -6px;
            border-width: 8px;
            border-style: solid;
            border-color: transparent transparent #cceabb transparent;
        }

        .tooltip:hover .tooltip_text {
            visibility: visible;
            opacity: 1;
        }
    </style>
</head>

<body>
    <div class="tooltip">GeeksforGeeks
        <span class="tooltip_text">
            A Computer science portal for geeks
        </span>
    </div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-417174-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200522200345/tooltip-final.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200522200345/tooltip-final.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200522200345/tooltip-final.mp4)</video>

最初，工具提示文本的不透明度设置为 0，然后过渡应用于延迟为 3s 的不透明度。
当我们悬停在**“极客暴发户”**文本上时，工具提示在 3s 内 100%可见。这会导致淡入效果/动画。