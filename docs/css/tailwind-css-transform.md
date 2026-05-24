# 顺风 CSS 变换

> 原文:[https://www.geeksforgeeks.org/tailwind-css-transform/](https://www.geeksforgeeks.org/tailwind-css-transform/)

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的属性都以类的形式被覆盖。此类用于控制任何元素的转换行为。在 CSS 中，我们可以通过使用 [CSS 变换属性](https://www.geeksforgeeks.org/css-transform-property/)来实现。

**转换类:**

*   **变换:**要执行任何变换，必须使用这个类。
*   **变换-gpu:** 通过使用这个类，变换将在 CPU 上的 gpu 上执行，CPU 将以更舒缓的方式执行。
*   **变换-无:**此类用于停用变换效果。

**语法:**

```html
<element class="transform-{trans-on}">...</element>
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
    <b>Tailwind CSS Transform Class</b> 
    <div class="bg-green-300 
                mx-16 
                space-y-4 
                p-2 
                justify-between 
                grid grid-rows-1 
                grid-flow-col"> 

    <div title="bg-left-top"
        class="bg-no-repeat
               w-16 h-16
               my-4 transform skew-y-12" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div title="bg-left"
        class="bg-no-repeat 
               w-16 h-16
               my-4 transform rotate-45" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div title="bg-left-bottom"
        class="bg-no-repeat 
               w-16 h-16 
               my-4 transform scale-50" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div title="bg-left-bottom"
        class="bg-no-repeat 
               w-16 h-16 
               my-4 transform translate-x-4 translate-y-4" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    </div> 
</body> 
</html>
```

**输出:**

![](img/9f3ef6b2866be80af73c1cc3c2fd336f.png)

顺风 CSS 变换类