# 顺风 CSS 最小宽度

> 原文:[https://www.geeksforgeeks.org/tailwind-css-min-width/](https://www.geeksforgeeks.org/tailwind-css-min-width/)

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的属性都以类的形式被覆盖。它是 [CSS 最小宽度属性](https://www.geeksforgeeks.org/css-min-width-property/)的替代品。此类用于定义元素的最小宽度。宽度值不能小于*最小宽度*的值。如果元素中指定的内容较小，*最小宽度*保持指定的最小宽度。

**最小宽度等级:**

*   **min-w-0:** 此类用于设置 *min-width* 的长度。
*   **最小-w-full:** 此类用于设置满负荷时*最小宽度*的长度。
*   **min-w-min:** 此类用于将 *min-width* 的长度设置为最小容量。
*   **最小-最大宽度:**该等级用于设置最大容量时*最小宽度*的长度。

**语法:**

```html
<element class="min-w-0">...</element>
```

**示例:**宽度会根据屏幕大小变化。

## 超文本标记语言

```html
<!DOCTYPE html> 
<head> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center mx-4 space-y-2"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS MIn-Width Class</b> 
    <div class="w-24 h-16 min-w-full md:min-w-0 
                bg-green-400 rounded-lg text-white">
    </div>
</body> 

</html>
```

**输出:**

![](img/1ea0cd9791b54f3245baf91738017d90.png)