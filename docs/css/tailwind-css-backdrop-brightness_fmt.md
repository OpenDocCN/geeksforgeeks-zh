# 顺风 CSS 背景亮度

> 原文: [https://www.geeksforgeeks.org/tailwind-css-backdrop-brightness/](https://www.geeksforgeeks.org/tailwind-css-backdrop-brightness/)

背景亮度类别用于设置图像的亮度。这个类使用图像的线性乘数来增加或减少亮度。顺风 CSS 在 2.1 版本中新增了特色亮度。

## 背景亮度等级

*   `backdrop-brightness-0`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(0)`。
*   `backdrop-brightness-50`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(0.5)`。
*   `backdrop-brightness-75`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(0.75)`。
*   `backdrop-brightness-90`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(0.9)`。
*   `backdrop-brightness-95`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(0.95)`。
*   `backdrop-brightness-100`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(1.0)`。
*   `backdrop-brightness-105`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(1.05)`。
*   `backdrop-brightness-110`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(1.10)`。
*   `backdrop-brightness-125`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(1.25)`。
*   `backdrop-brightness-150`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(1.50)`。
*   `backdrop-brightness-200`: 这个类用来设置一个元素上的亮度，相当于 CSS `brightness(2.0)`。

## 语法

```html
<element class="backdrop-filter 
                backdrop-brightness-{amount}">
..
</element>
```

## 示例

```html
<!DOCTYPE html>
<html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^2.1/dist/tailwind.min.css"
        rel="stylesheet">
</head>

<body class="text-center mx-4 ">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Backdrop Brightness Class</b>
    <div class=" mx-16 mt-18 h-36 relative">
        <div class="absolute w-full py-18">
            <img class="rounded-lg object-cover" 
                  src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210605213323/Screenshot20210605213311.png" 
             alt="image">
        </div>
        <div class="relative h-32 flex overflow-x-auto space-x-4">
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-brightness-75 w-1/3">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-brightness-105 w-1/3">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-brightness-150 w-1/3">
            </div>
        </div>
    </div>
</body>

</html>
```

## 输出

![](img/36a6119f13884b41a72f636cd39a86f2.png)