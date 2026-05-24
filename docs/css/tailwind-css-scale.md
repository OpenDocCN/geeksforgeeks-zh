# 顺风 CSS 音阶

> 原文:[https://www.geeksforgeeks.org/tailwind-css-scale/](https://www.geeksforgeeks.org/tailwind-css-scale/)

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的功能属性都以类的形式被覆盖。此类用于调整 2D 平面中元素的大小。它在水平和垂直方向上缩放元素。在 CSS 中，我们可以通过使用 [CSS 标尺()功能](https://www.geeksforgeeks.org/css-scale-function/)来做到这一点。

**等级等级:**

*   **刻度-0 | 50 | 75 | 90 | 95 | 100 | 105 | 110 | 125 | 150:**此类用于在两个轴上按百分比进行刻度。
*   **scale-x-0 | 50 | 75 | 90 | 95 | 100 | 105 | 110 | 125 | 150:**此类用于在 x 轴上按百分比进行缩放。
*   **scale-y-0 | 50 | 75 | 90 | 95 | 100 | 105 | 110 | 125 | 150:**此类用于在 y 轴上按百分比进行缩放。

**语法:**

```html
<element class="scale-{axis-percentage}">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
<head> 
    <link href= 
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold"> 
       GeeksforGeeks 
    </h1> 
    <b>Tailwind CSS Scale Class</b> 
    <div class="bg-green-300 
                mx-16
                p-4
                justify-between 
                grid grid-flow-col"> 
    <div class="bg-no-repeat
                w-16 h-16 transform scale-50" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div class="bg-no-repeat 
                w-16 h-16 transform scale-75" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    <div class="bg-no-repeat 
                w-16 h-16 transform scale-100" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div class="bg-no-repeat 
                w-16 h-16 transform scale-125" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    </div> 
</body> 
</html> 
```

**输出:**

![](img/3634142a24adf2eb8af0a25e8f440f49.png)

CSS 缩放类