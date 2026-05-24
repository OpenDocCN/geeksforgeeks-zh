# CSS 滚动-填充-内嵌属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-padding-inline-property/](https://www.geeksforgeeks.org/css-scroll-padding-inline-property/)

*滚动-填充-内联*属性用于一次性将所有滚动填充设置到内联维度中滚动元素或容器的开始和结束。该属性是*滚动-填充-内联-开始*和*滚动-填充-内联-结束*属性的简写。

开始侧和结束侧的选择取决于写入模式。对于*水平-tb* 写入模式，开始侧和结束侧分别是左侧和右侧。同样，对于*垂直-rl* 或*垂直-lr* 书写模式，开始侧和结束侧分别是顶侧和底侧，其中*水平-tb* 代表*水平从上到下*，*垂直-rl* 是从右到左的垂直，而*垂直-lr* 是从左到右的垂直*。*

**语法:**

```html
scroll-padding-block-end: keyword_values
```

或者

```html
scroll-padding-block-end: length_values
```

或者

```html
scroll-padding-block-end: Global_Values

```

**属性值:**该属性接受上面提到的和下面描述的三个属性。

*   **length_values:** 该属性是指用长度单位定义的值。例: *px、em、vh、%* 等。
*   **关键字 _ 值:**该属性是指用*汽车*等单位定义的关键字 _ 值。一般来说，默认情况下这将被设置为 0px，但如果非零值更合适，它也可以是非零值。
*   **Global_Values:** 该属性是指*继承、初始、取消设置*等全局值。

**示例:**在本例中，您可以通过滚动到示例内容的两个“界面”中间的点来查看*滚动-填充-内联*的效果。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .img {
            width: 275px;
            height: 300px;
            scroll-snap-align: none start;
        }

        .GeeksforGeeks {
            width: 300px;
            height: 300px;
            border: 2px solid red;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
        }
    </style>
</head>

<body>

    <div class="GeeksforGeeks" 
        style="scroll-padding-inline: 100px;">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
            class="img">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png"
            class="img">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png"
            class="img">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png"
            class="img">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
            class="img">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png"
            class="img">
    </div>
</body>

</html>
```

**输出:**

![](img/38f4390f6a4df5fb7b813bdd433d1b61.png)

**支持的浏览器:**

*   火狐浏览器
*   铬
*   边缘
*   歌剧
*   Safari(不支持)
*   互联网浏览器(不支持)