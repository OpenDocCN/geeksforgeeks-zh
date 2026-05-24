# CSS 滚动-左边距属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-margin-left-property/](https://www.geeksforgeeks.org/css-scroll-margin-left-property/)

**向左滚动边距**属性用于一次性设置一个元素左侧的所有滚动边距。为**左边距**指定的值决定了主要在支持范围之外的页面应该保持多少可见。

因此，**向左滚动边距**值代表定义滚动捕捉区域的外排，该区域用于将该框捕捉到支架。

**语法:**

```html
scroll-margin-left: length
/* Or */
scroll-margin-left: Global_Values

```

**属性值:**该属性接受上面提到的和下面描述的两个属性:

*   **长度**:该属性是指用长度单位定义的值:px、em、rem、vh 等。
*   **Global_Values:** 该属性是指继承、取消设置、初始等全局值。

**注意:**向左滚动边距不接受百分比值作为长度。

**示例:**在本例中，您可以通过滚动到示例内容的两个“界面”中间的点来查看**向左滚动边距**的效果。

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            .img {
                width: 296px;
                height: 275px;
                scroll-snap-align: none end;
            }
            .photo {
                width: 300px;
                height: 300px;
                overflow-x: auto;
                overflow-y: hidden;
                white-space: nowrap;
                scroll-snap-type: x mandatory;
            }
        </style>
    </head>
    <body>
        <div class="photo">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img8.jpeg" 
                 class="img" 
                 style="scroll-margin-left: 1rem;" />

            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" 
                 class="img" 
                 style="scroll-margin-left: 2rem;" />

            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131445/img1-300x214.jpg" 
                 class="img" 
                 style="scroll-margin-left: 3rem;" />

            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131447/img9.jpeg" 
                 class="img"
                 style="scroll-margin-left: 4rem;" />
        </div>
    </body>
</html>
```

**输出:**

![](img/5be8caf227d668c2c994bbbb8a30047a.png)

**支持的浏览器:**

*   铬
*   火狐浏览器
*   边缘
*   歌剧
*   Safari(部分支持)
*   互联网浏览器(不支持)