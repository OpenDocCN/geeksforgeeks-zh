# CSS 暂停后属性

> 原文:[https://www.geeksforgeeks.org/css-pause-after-property/](https://www.geeksforgeeks.org/css-pause-after-property/)

CSS 暂停后属性用于定义元素后的暂停时间。这个属性可以看作是语音媒体，相当于视觉媒体中的页边空白属性。

**语法:**

```html
pause-after: time | percentage;

```

**参数:**该属性接受两个参数，如上所述，如下所述:

*   **Time:** This parameter holds a value, and the pause will be the length of the specified value.
*   **Percentage:** The length of pause depends on the value of speech speed. If it is set to 50% after pause, it will generate 250 milliseconds.

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            audio {
                 pause-after : 20ms;
            }
        </style>
    </head>
    <body style="text-align: center;">
        <h1 style="color: green;">GeeksforGeeks</h1>

<p>CSS pause-after Property</p>

        <audio controls> 
        <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3"> 
    </audio> 
    </body>
</html>
```