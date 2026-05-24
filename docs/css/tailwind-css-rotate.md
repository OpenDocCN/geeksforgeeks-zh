# 顺风 CSS 旋转

> 原文:[https://www.geeksforgeeks.org/tailwind-css-rotate/](https://www.geeksforgeeks.org/tailwind-css-rotate/)

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的属性都以类的形式被覆盖。此类用于根据给定的角度作为参数旋转元素。角度可以用度数、弧度或圈数来设定。在 CSS 中，我们可以通过使用 [CSS 旋转()功能](https://www.geeksforgeeks.org/css-rotate-function/)来实现。

**轮岗班:**

*   **旋转-0:** 此类为无旋转。
*   **旋转-1:** 此类用于顺时针旋转 1 度。
*   **旋转-2:** 此类用于顺时针旋转 2 度。
*   **旋转-3:** 此类用于顺时针旋转 3 度。
*   **旋转-6:** 此类用于顺时针旋转 6 度。
*   **旋转-12:** 此类用于顺时针旋转 12 度。
*   **旋转-45:** 此类用于顺时针旋转 45 度。
*   **旋转-90:** 此类用于顺时针旋转 90 度。
*   **旋转-180:** 此类用于顺时针旋转 180 度。
*   **-旋转-1:** 此类用于逆时针旋转 1 度。
*   **-旋转-2:** 此类用于逆时针旋转 2 度。
*   **-旋转-3:** 此类用于逆时针旋转 3 度。
*   **-旋转-6:** 此类用于逆时针旋转 6 度。
*   **-旋转-12:** 此类用于逆时针旋转 12 度。
*   **-旋转-45:** 此类用于逆时针旋转 45 度。
*   **-旋转-90:** 此类用于逆时针旋转 90 度。
*   **-旋转-180:** 此类用于逆时针旋转 180 度。

**语法:**

```html
<element class="rotate-{degree}">...</element>
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
    <b>Tailwind CSS Rotate Class</b> 
    <div class="bg-green-300 
                mx-16
                p-4
                justify-between 
                grid grid-flow-col"> 
    <div class="bg-no-repeat
                w-16 h-16 transform rotate-0" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div class="bg-no-repeat 
                w-16 h-16 transform rotate-45" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    <div class="bg-no-repeat 
                w-16 h-16 transform rotate-90" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div class="bg-no-repeat 
                w-16 h-16 transform rotate-180" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    </div> 
</body> 
</html> 
```

**输出:**

![](img/2a1fdc856506cd4760439743e8f99fca.png)