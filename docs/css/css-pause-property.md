# CSS 暂停属性

> 原文:[https://www.geeksforgeeks.org/css-pause-property/](https://www.geeksforgeeks.org/css-pause-property/)

CSS 暂停属性用于定义元素前后的暂停时间。pause 属性接受两个值 pause-before 和 pause-after。如果只提供一个值，则它适用于两个属性。

**语法:**

```html
pause: <'pause-before'> <'pause-after'>

```

**参数:**该属性是上面提到的和下面描述的另外两个属性的组合:

*   **[Before pause:](https://www.geeksforgeeks.org/css-pause-before-property/ ‎)** This parameter holds the value of the attribute before pause, such as 10ms.
*   **[After pause:](https://www.geeksforgeeks.org/css-pause-after-property/)** This parameter stores the value of the attribute after pause, such as 10ms.

**示例 1:** 在此示例中，暂停 20 毫秒，包括之前和之后。

## HTML

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            audio {
                 pause : 20ms;
            }
        </style>
    </head>
    <body style="text-align: center;">
        <h1 style="color: green;">GeeksforGeeks</h1>

<p>CSS pause Property</p>

        <audio controls> 
        <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3"> 
    </audio> 
    </body>
</html>
```