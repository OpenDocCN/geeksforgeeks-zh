# 如何使用 Tailwind CSS 填充剩余的屏幕高度？

> 原文:[https://www . geeksforgeeks . org/如何使用 tailwind-css 填充剩余的屏幕高度/](https://www.geeksforgeeks.org/how-to-fill-up-the-rest-of-screen-height-using-tailwind-css/)

在本文中，我们将学习如何使用 [Tailwind CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 填充屏幕高度的剩余部分。

**方法:**为了解决上述问题，我们将使用顺风 CSS 的[伸缩类](https://www.geeksforgeeks.org/tailwind-css-flex/)和[高度类](https://www.geeksforgeeks.org/tailwind-css-height/)。

我们将用来解决这个问题的类如下。

*   **flex:** 用于设置柔性物品的长度。 *flex* 级反应灵敏，移动友好。
*   **伸缩栏:**用于垂直定位伸缩项。
*   **h-screen:** 这个类用来让一个元素跨越视口的整个高度。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link href=
"https://unpkg.com/tailwindcss@1.8.12/dist/tailwind.min.css"
        rel="stylesheet" />
</head>

<body>
    <div class="flex flex-col h-screen">
        <div class="bg-yellow-500 py-8 hidden sm:block ">
            <div class="flex space-x-4">
                <a href="#" class="bg-gray-900 text-white 
                        px-3 py-2 rounded-md text-sm 
                        font-medium" aria-current="page">
                    GeeksForGeeks Dashboard
                </a>

                <a href="#" class="text-gray-300 
                        hover:bg-gray-700 
                        hover:text-white px-3 py-2 
                        rounded-md text-sm font-medium">
                    Team
                </a>

                <a href="#" class="text-gray-300 
                        hover:bg-gray-700
                        hover:text-white px-3 py-2 
                        rounded-md text-sm font-medium">
                    Projects
                </a>

                <a href="#" class="text-gray-300 
                        hover:bg-gray-700 hover:text-white 
                        px-3 py-2 rounded-md 
                        text-sm font-medium">
                    Calendar
                </a>
            </div>
        </div>

        <div class="bg-green-500 flex flex-grow">
            This is the other content on screen
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/60e9782d84ed6c8c2e000eafa6d47e9c.png)