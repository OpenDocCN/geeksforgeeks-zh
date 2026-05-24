# 泰国风 CSS 变蓝

> 原文:[https://www.geeksforgeeks.org/tailwind-css-blur/](https://www.geeksforgeeks.org/tailwind-css-blur/)

模糊类用于在图像上应用模糊效果滤镜。在 CSS 中，我们通过使用 [CSS 模糊()函数](https://www.geeksforgeeks.org/?p=330386)来实现。顺风 CSS 在 2.1 版本中新增了模糊功能。

**模糊:**

*   **模糊-0:** 这个类相当于 CSS 中没有模糊效果的模糊(0)。
*   **模糊-sm:** 这个类相当于 CSS 中作为模糊(4px)的小模糊效果。
*   **模糊:**这个类相当于 CSS 中作为模糊(8px)的普通模糊效果。
*   **模糊-md:** 这个类相当于 CSS 中的模糊(12px)那样的中等模糊效果。
*   **模糊-lg:** 这个类相当于 CSS 中的大模糊效果为模糊(16px)。
*   **模糊-xl:** 这个类相当于 CSS 中作为模糊(24px)的超大模糊效果。
*   **模糊-2xl:** 这个类相当于 CSS 中模糊(40px)的两倍超大模糊效果。
*   **模糊-3xl:** 这个类相当于 CSS 中模糊(64px)的三倍超大模糊效果。

**语法:**

```html
<element class="filter blur-{amount}">..</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^2.1/dist/tailwind.min.css"
        rel="stylesheet">
</head>

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Blur Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter blur-0"
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg"
             alt="image">
        <img class="rounded-lg filter blur-sm"
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg"
             alt="image">
        <img class="rounded-lg filter blur-md"
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg"
             alt="image">
        <img class="rounded-lg filter blur-lg"
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg"
             alt="image">
        <img class="rounded-lg filter blur-xl"
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg"
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/b4a14207d20534f6e9c482fb231945c3.png)