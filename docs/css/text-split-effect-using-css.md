# 使用 CSS 的文本分割效果

> 原文:[https://www.geeksforgeeks.org/text-split-effect-using-css/](https://www.geeksforgeeks.org/text-split-effect-using-css/)

在本文中，我们将看到如何使用 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 创建文本分割效果。HTML 代码用于创建各部分的基本结构，CSS 代码用于设置样式。

**进场:**

*   用类“容器”创建一个 HTML [div](https://www.geeksforgeeks.org/div-tag-html/) 元素。
*   在“容器”里面，用类“盒子”创建一个 HTML [div](https://www.geeksforgeeks.org/div-tag-html/) 。
*   用文本创建两个 [p](https://www.geeksforgeeks.org/html-paragraph/) 标签。
*   为了分割文本，我们将使用[剪辑路径](https://www.geeksforgeeks.org/animation-using-clip-path-property-in-css/)提供文本形状，然后在悬停时使用[变换](https://www.geeksforgeeks.org/css-transform-property/)属性来翻译它。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style type="text/css">

    /* Aligining container in center*/
    .container {
        position: absolute;
        transform: translate(-50%, -50%);
        top: 35%;
        left: 35%;
        color: green;
    }

    /* General styling to text and 
       transition of 2s*/    
    .text {
        position: absolute;
        text-transform: uppercase;
        font-size: 3rem;
        transition: 2s ease;
    }

    /* Giving shapes to text using clip-path*/    
    .text1 {
        clip-path: polygon(0 0, 100% 0,
             100% 100%, 50% 0, 0 100%);
    }

    .text2 {
        clip-path: polygon(0 100%, 50% 0, 
           100% 100%, 100% 100%, 0 100%);
    }

    /* transforming box 1 position on hover */    
    .box:hover .text1 {
        transform: translateY(-10px);
    }

    /* transforming box 2 position on hover */    
    .box:hover .text2 {
        transform: translateY(10px);
    }
    </style>
</head>

<body>

    <!-- Create container -->
    <div class="container">

        <!-- create div with class box -->
        <div class="box">

            <!-- write the text to be splitted 
                 into two p tags -->
            <p class="text text1">geeksforgeeks</p>

            <p class="text text2">geeksforgeeks</p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/d6461827f89b7ce38cf33b9524055d36.png)

**参考:**[**https://www . geeksforgeeks . org/how-split-text-horizontal-on-move-over-use-CSS/**](https://www.geeksforgeeks.org/how-to-split-text-horizontally-on-mouse-move-over-using-css/)