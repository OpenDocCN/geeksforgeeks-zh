# 顺风 CSS 网格行开始/结束

> 原文:[https://www . geesforgeks . org/tail wind-CSS-grid-row-start-end/](https://www.geeksforgeeks.org/tailwind-css-grid-row-start-end/)

这个类在顺风 CSS 中接受多个值。所有的属性都包含在类的形式中。是 CSS 中 [CSS 网格行属性](https://www.geeksforgeeks.org/css-grid-row-property/)的替代。它用于描述允许设计网格结构和使用 Tailwind CSS 控制网格项目放置的属性数量。它可以改变网格项目的布局，而不考虑它们的源顺序，这允许移动网格项目以适应这些变化的上下文，而不必修改底层标记。但是为了前端的快速发展。行数由给这个类的值的数量来设置。

**网格行开始/结束:**

*   **行自动**
*   **行-跨度-1**
*   **行跨-2**
*   **排-跨-3**
*   **行跨-4**
*   **行跨-5**
*   **行跨-6**
*   **行-跨度-7**
*   **行-跨度-8**
*   **排跨-9**
*   **排距-10**
*   **排-跨-11**
*   **排跨-12**
*   **全排跨**
*   **行-开始-1**
*   **行-开始-2**
*   **行-开始-3**
*   **行-开始-4**
*   **行-开始-5**
*   **行-开始-6**
*   **行-开始-7**
*   **行-开始-8**
*   **行-开始-9**
*   **行-开始-10**
*   **行-开始-11**
*   **行-开始-12**
*   **行-开始-13**
*   **行-启动-自动**
*   **行-结束-1**
*   **行-结束-2**
*   **行-结束-3**
*   **行-结束-4**
*   **行-结束-5**
*   **行-结束-6**
*   **行-结束-7**
*   **行-结束-8**
*   **行-结束-9**
*   **行-结束-10**
*   **行-结束-11**
*   **行-结束-12**
*   **行-结束-13**
*   **行-结束-自动**

**跨度行(row-span):** 这个类会覆盖跨度区域，提到数字后这个类会持有一个跨度的面积，我们都知道有 12 个网格行或者你可以说 12 个网格跨度。

**语法:**

```html
<element class="row-span-number"> Contents... </element>
```

**参数:**这个类接受一个参数，如上所述，如下所述:

**数字:**它代表一个网格行的跨度数。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<head> 
    <title>Tailwind row-span Class</title> 

    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 

    <b>Tailwind CSS row-span Class</b> 

    <div id="main" class="m-8 grid grid-row-3 grid-flow-col gap-1"> 
        <div class="bg-green-300 rounded-lg">1</div> 
        <div class="bg-green-300 rounded-lg">2</div> 
        <div class="bg-green-300 rounded-lg">3</div> 
        <div class="bg-green-500 row-span-2 rounded-lg">4</div> 
        <div class="bg-green-300 rounded-lg">5</div> 
        <div class="bg-green-500 row-span-3 rounded-lg">6</div> 
    </div> 
</body> 

</html>
```

**输出:**

![](img/4c391cb40adb65fa83e439b42187471b.png)

**开始和结束线(行-开始|结束):**这个类用于使一个元素在第 n 个网格线开始或结束。这些也可以与行跨度数实用程序结合使用，以跨越特定数量的列。

**注意:**我们可以将这个类和上述的类(span columns(row-span))合并，下面的例子会给你一个如何使用的思路。

**语法:**

```html
<element class="row-start|end-number">..</element>
```

**参数:**这个类接受一个参数，如上所述，如下所述:

**编号:**此参数定义网格行或正常行的开始或结束位置。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 

<head> 
    <title>Tailwind row-start|end Class</title> 

    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 

    <b>Tailwind CSS row-start|end Class</b> 

    <div id="main" class="m-8 grid grid-row-4 
                          grid-flow-col gap-1 "> 
        <div class="bg-green-500 row-start-2 row-span-2 
                    rounded-lg">1</div> 
        <div class="bg-green-300 rounded-lg">2</div> 
        <div class="bg-green-300 rounded-lg">3</div> 
        <div class="bg-green-500 row-start-2 col-end-4 
                    rounded-lg">4</div> 
        <div class="bg-green-300 rounded-lg">5</div> 
        <div class="bg-green-300 rounded-lg">6</div> 
        <div class="bg-green-300 rounded-lg">7</div> 
        <div class="bg-green-500 row-start-2 row-span-3 
                    rounded-lg">8</div>
    </div> 
</body> 

</html>
```

**输出:**

![](img/911157c82ce2410a541d290d28fee39b.png)