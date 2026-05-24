# CSS 滚动-对齐属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-snap-align-property/](https://www.geeksforgeeks.org/css-scroll-snap-align-property/)

CSS **滚动-对齐-对齐**属性表示元素或容器的对齐端口内的框的对齐区域的对齐位置。

**语法:**

```html
scroll-snap-align: Keyword_Values;
/* Or */
scroll-snap-align: Global_Values;

```

**属性值:****滚动-对齐-对齐**属性接受上面提到的和下面描述的两个值:

*   **关键字 _ 值:**该属性指的是*无、开始、结束、中心、*等关键字值。
*   **Global_Values:** 该属性是指*继承、初始、取消设置、*等全局值。

**注意:**当设置了两个属性值时，那么第一个用于块，第二个用于内联。《出埃及记》*滚动-对齐:开始结束；*

**示例 1:** 在此示例中，您可以通过滚动到示例内容的两个“界面”中间的一点来查看**滚动-对齐-对齐**的效果。这里我们使用了*无开始*作为属性值。

```html
<!DOCTYPE html>
<html>

    <head>
        <style>

            .geeks {
                width: 255px;
                height: 300px;
                border:4px solid greenyellow;
                scroll-snap-align: none start;
            }
            .Container {
                width: 300px;
                height: 300px;
                border:5px solid red;
                overflow-x: auto;
                overflow-y: hidden;
                white-space: nowrap;
                scroll-snap-type: x mandatory;
                scroll-snap-stop: always;
            }

        </style>
    </head>

<body>

    <div class="Container">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png"
        class="geeks">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" 
        class="geeks">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" 
        class="geeks">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png"
        class="geeks">

    </div>

</body>

</html>
```

**输出:**

![](img/69428d86bc74ff40f5fafd2510875655.png)

**支持的浏览器:**

*   铬合金。
*   火狐。
*   狩猎。
*   边缘。
*   歌剧。
*   互联网浏览器(不支持)。