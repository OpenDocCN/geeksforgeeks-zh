# CSS 提示后属性

> 原文:[https://www.geeksforgeeks.org/css-cue-after-property/](https://www.geeksforgeeks.org/css-cue-after-property/)

**CSS 提示后属性**用于定义在元素后播放的听觉图标，以区分和设置元素。

**语法:**

```html
cue-after: url | none ;

```

**参数:**该属性接受两个值，如上所述，如下所述:

*   **URL:** This parameter stores audio icon resources. If the user can't present the mentioned auditory icon, it will generate an alternative prompt, such as a bell.
*   **None:** This parameter defines that auditory icons are not used.

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .gfg {
            cue-after: none;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>
    <p class="gfg">CSS cue-after Property</p>

    <audio controls>
        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3">
    </audio>
</body>

</html>
```