# CSS 滚动-填充-内联-结束属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-padding-inline-end-property/](https://www.geeksforgeeks.org/css-scroll-padding-inline-end-property/)

*滚动填充内联结束*属性用于一次性将所有滚动填充设置到内联维度中滚动元素或容器的结束边缘。端侧分别是*水平-tb* 写入模式的右侧和*垂直-lr* 或*垂直-rl* 写入模式的底部或顶部。其中*水平-tb* 代表水平从上到下，*垂直-rl* 代表*垂直从右到左*，*垂直-lr* 代表*垂直从左到右*。

**语法:**

```html
scroll-padding-inline-end: keyword_values
```

或者

```html
scroll-padding-inline-end: length_values
```

或者

```html
scroll-padding-inline-end: Global_Values
```

**属性值:**该属性接受上面提到的和下面描述的三个属性。

*   **length_values:** 该属性是指用长度单位 exp 定义的值: *px，em，vh，%* 等。
*   **Global_Values:** 该属性是指*继承、初始、取消设置*等全局值。
*   **关键字 _ 值:**该属性是指*关键字 _ 值*，用*汽车*等单位定义。一般来说，这将被设置为 0px 默认情况下，但它可以是非零值，以及如果非零值是更合适的。

**示例:**在本例中，您可以通过滚动到示例内容的两个界面中间的点来查看*滚动-填充-内联-结束*属性的效果。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geeks {
            width: 300px;
            height: 270px;
            scroll-snap-align: none end;
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
        "scroll-padding-inline-end: 90px;">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img8.jpeg"
            class="geeks">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
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

![](img/5bafb954f78a77bf076a541dcde24017.png)

**支持的浏览器:**

*   火狐浏览器
*   铬
*   边缘
*   歌剧

**注意:**不支持 Internet Explorer 和 Safari。