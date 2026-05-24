# 顺风 CSS 背景剪辑

> 原文:[https://www.geeksforgeeks.org/tailwind-css-background-clip/](https://www.geeksforgeeks.org/tailwind-css-background-clip/)

该类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受多个值，其中所有属性都以类的形式覆盖。它是 [CSS 背景剪辑属性](https://www.geeksforgeeks.org/css-background-clip-property/)的替代品。此属性用于定义如何在元素中扩展背景(颜色或图像)。

**背景剪辑类:**

*   **bg-clip-border:** 这个类用来设置覆盖整个分区的背景色。
*   **bg-clip-padding:** 这个类用来设置边框内部的背景。
*   **bg-clip-content:** 此类仅用于设置内容的背景颜色。
*   **bg-clip-text:** 这个类用于裁剪元素的背景以匹配文本的形状。对于希望背景图像在文本中可见的效果非常有用。

**语法:**

```html
<element class="bg-clip-{Clip type}">...</element>
```

**示例:**

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
    <b>Tailwind CSS 
    <span class="bg-clip-text text-lg text-transparent 
                 bg-gradient-to-r
                 from-green-400 to-blue-500">
        Background Clip Class
        </span>
    </b> 
    <div class="mx-2 grid grid-cols-3 gap-2 bg-green-200 rounded-lg">
        <div class="bg-clip-border p-6 bg-green-600 border-dashed
                    border-4 border-green-300">
        </div>
        <div class="bg-clip-padding p-6 bg-green-600 border-dashed
                    border-4 border-green-300">

        </div>
        <div class="bg-clip-content p-6 bg-green-600 border-dashed
                    border-4 border-green-300">

        </div>
    </div>
</body> 

</html> 
```

**输出:**

![](img/516653684ee3c026ada83ae6d741144c.png)