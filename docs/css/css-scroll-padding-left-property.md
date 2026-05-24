# CSS 滚动-填充-左侧属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-padding-left-property/](https://www.geeksforgeeks.org/css-scroll-padding-left-property/)

*向左滚动填充*属性用于一次性设置滚动容器或元素左侧的所有填充。为*向左滚动填充*指定的值决定了主要在快照排序之外的页面应该保持多少可见。

**语法:**

```html
scroll-padding-left:length_values
```

或者

```html
scroll-padding-left:keyword_values
```

或者

```html
scroll-padding-left:Global_Values

```

**属性值:**该属性接受上面提到的和下面描述的三个属性。

*   **length_values:** 该属性是指用长度单位定义的值。例: *px、em、vh、%* 等。
*   **关键字 _ 值:**该属性是指*关键字 _ 值*，用*汽车*等单位定义。一般来说，默认情况下这将设置为 0px，但如果非零值更合适，它也可以是非零值。
*   **Global_Values:** 该属性是指*继承、初始、取消设置、*等全局值。

**示例:**以下示例说明了*向左滚动填充*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            width: 275px;
            height: 300px;
            border: 2px solid red;
            scroll-snap-align: none start;
        }

        .GeeksforGeeks {
            width: 300px;
            height: 300px;
            border: 2px solid green;
            text-align: center;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
        }
    </style>
</head>

<body>
    <div class="GeeksforGeeks" style=
            "scroll-padding-left: 80px;">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
            class="geek">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png"
            class="geek">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png"
            class="geek">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png"
            class="geek">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg"
            class="geek">
    </div>
</body>

</html>
```

**输出:**

![](img/126b233a9d7a7b43e4029e5a2ca9119d.png)

**支持的浏览器:**

*   铬
*   火狐浏览器
*   歌剧
*   边缘
*   Safari(部分支持)
*   互联网浏览器(不支持)