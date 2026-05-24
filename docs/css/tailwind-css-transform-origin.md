# 顺风 CSS 变换原点

> 原文:[https://www . geesforgeks . org/tail wind-CSS-transform-origin/](https://www.geeksforgeeks.org/tailwind-css-transform-origin/)

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的属性都以类的形式被覆盖。此类用于指定元素旋转的原点。它是元素旋转的点。它可以用于 2D 和三维旋转。在 CSS 中，我们可以通过使用 [CSS 变换源属性](https://www.geeksforgeeks.org/css-transform-origin-property/)来实现。

**变换原点类:**

*   **原点-中心:**该类用于将元素的原点设置为中心。
*   **原点-顶部:**该类用于将元素的原点设置为顶部。
*   **原点-右上角:**该类用于将元素的原点设置为右上角。
*   **原点-右侧:**该类用于将元素的原点设置为右侧。
*   **原点-右下角:**该类用于将元素的原点设置为右下角。
*   **原点-底部:**此类用于将元素的原点设置为底部。
*   **原点-左下:**这个类用于将元素的原点设置为左下。
*   **原点-左侧:**这个类用于将元素的原点设置为左侧。
*   **原点-左上角:**该类用于将元素的原点设置为左上角。

**语法:**

```html
<element class="origin-{keyword}">...</element>
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
    <b>Tailwind CSS Transform Origin Class</b> 
    <div class="bg-green-300 
                mx-16
                p-4
                justify-between 
                grid grid-flow-col"> 
    <div class="bg-yellow-500 w-16 h-16">
    <div class="bg-no-repeat
                w-16 h-16 origin-center
                transform rotate-45" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    </div>
    <div class="bg-yellow-500 w-16 h-16">
    <div class="bg-no-repeat 
                w-16 h-16 origin-top-left
                transform rotate-45" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    </div>
    <div class="bg-yellow-500 w-16 h-16">
    <div class="bg-no-repeat 
                w-16 h-16 origin-bottom-right 
                transform rotate-45" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    </div>
    <div class="bg-yellow-500 w-16 h-16">
    <div class="bg-no-repeat 
                w-16 h-16 origin-left
                transform rotate-45" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    </div>
    </div> 
</body> 
</html> 
```

**输出:**

![](img/d2060208c720ce199ff5f385d44b0d01.png)