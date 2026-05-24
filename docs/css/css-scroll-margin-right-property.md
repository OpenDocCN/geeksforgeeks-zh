# CSS 滚动-右边距-属性

> 原文:[https://www . geesforgeks . org/CSS-scroll-margin-right-property/](https://www.geeksforgeeks.org/css-scroll-margin-right-property/)

**向右滚动边距**属性用于一次将所有滚动边距设置到一个元素的右侧。为**右边距**指定的值决定了主要在快照之外的页面应该保持多少可见。

因此，**向右滚动边距**值代表定义滚动捕捉区域的外排，该区域用于将此框捕捉到捕捉端口。

**语法:**

```html
scroll-margin-right: length
/* Or */
scroll-margin-right: Global_Value

```

**属性值:**该属性接受上面提到的和下面描述的两个属性:

*   **长度:**该属性是指用长度单位 exp: px、em、vh 等定义的值。
*   **Global_Values:** 该属性是指继承、初始、取消设置等全局值。

**注意:** **滚动-边距-右侧**不接受百分比值作为长度。

**示例:**在本例中，您可以通过滚动到示例内容的两个“界面”中间的点来查看**向右滚动边距**的效果。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        img {
              width:300px;
              height:280px;
              scroll-snap-align: none end;
        }
        .Gallery {
              width: 300px;
              height:300px;
              overflow-x: auto;
              overflow-y: hidden;
              white-space: nowrap;
              scroll-snap-type: x mandatory;
        }
    </style>
</head>
<body>
    <div class="photoGallery">

          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" 
          style="scroll-margin-right: 50px;">

          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" 
          style="scroll-margin-right: 60px;">

          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" 
          style="scroll-margin-right: -50px;">

    </div>
</body>
</html>
```

**输出:**

![](img/e99c929abea33a394b62ccd9c8811d00.png)

**支持的浏览器:**

*   铬
*   火狐浏览器
*   歌剧
*   Safari(部分支持)
*   边缘
*   互联网浏览器(不支持)