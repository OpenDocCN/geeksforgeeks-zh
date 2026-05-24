# SVG `<switch>`元素

> 原文:[https://www.geeksforgeeks.org/svg-switch-element/](https://www.geeksforgeeks.org/svg-switch-element/)

开关**<>**SVG 元素用于按顺序评估其直接子元素的属性，然后渲染这些属性评估为真的第一个子元素。其他剩余的子级将不会被渲染。

**语法:**

```html
<switch attribute="" >
    <child 1>
    <child 2>
    <child 3>
    <child n>
</switch>

```

**属性:**

*   **全局属性:**使用了一些全局属性，如核心属性、造型属性等。

**例:**使用<开关>元素获取系统语言。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 -20 100 50">
        <switch>
            <text systemLanguage="en-us">
                US English
            </text>

            <text systemLanguage="en-au">
                Australian English
            </text>

            <text systemLanguage="en">
                Global English
            </text>

            <text systemLanguage="es">
                Spanish | Espanol
            </text>
        </switch>
    </svg>
</body>

</html>
```

**输出:**

![](img/aa0cddf4bc1c38cc9df55088d4e9b346.png)

**支持的浏览器:**此 SVG 元素支持以下浏览器:

*   铬
*   边缘
*   火狐浏览器
*   旅行队
*   微软公司出品的 web 浏览器
*   歌剧