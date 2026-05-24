# CSS 滚动-填充-内嵌-开始属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-padding-inline-start-property/](https://www.geeksforgeeks.org/css-scroll-padding-inline-start-property/)

*滚动-填充-内联-开始*属性用于一次性将所有滚动填充设置到内联维度中滚动元素或容器的开始边缘。起始侧分别是*水平-tb* 书写模式的左侧和*垂直-lr* 或*垂直-rl* 书写模式的顶部或底部，其中*水平-tb* 代表*水平从上到下*和*垂直-rl* 或*垂直-lr* 代表*垂直从右向左*和*垂直从左向右*

**语法:**

```html
scroll-padding-inline-start: keyword_values
```

或者

```html
scroll-padding-inline-start: length_values
```

或者

```html
scroll-padding-inline-start: Global_Values
```

**属性值:**该属性接受上面提到的和下面描述的三个属性。

*   **length_values:** 该属性是指用长度单位定义的值。例: *px、em、vh、%* 等。
*   **Global_Values:** 该属性是指*继承、初始、取消设置、*等全局值。
*   **关键字 _ 值:**该属性是指用*汽车*等单位定义的关键字 _ 值。一般来说，这将被设置为 0px 默认情况下，但它可以是非零值以及如果非零值是更合适的。

**示例:**在本例中，您可以通过滚动到示例内容的两个“界面”中间的某个点来查看*滚动-填充-内联-开始*的效果。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geeks {
            width: 270px;
            height: 300px;
            scroll-snap-align: none start;
        }

        .GeeksforGeeks {
            width: 300px;
            height: 300px;
            border: 2px solid green;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
        }
    </style>
</head>

<body>
    <div class="GeeksforGeeks" style=
        "scroll-padding-inline-start: 90px;">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
            class="geeks">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img8.jpeg"
            class="geeks">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png"
            class="geeks">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img8.jpeg"
            class="geeks">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
            class="geeks">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png"
            class="geeks">
    </div>
</body>

</html>
```

**输出:**

![](img/e9b5c03819b4ac349a5921305b7250f4.png)

**支持的浏览器:**

*   火狐浏览器
*   铬
*   边缘
*   歌剧
*   Safari(不支持)
*   互联网浏览器(不支持)