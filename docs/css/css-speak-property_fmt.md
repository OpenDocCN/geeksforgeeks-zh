# CSS speak 属性

> 原文: [https://www.geeksforgeeks.org/css-speak-property/](https://www.geeksforgeeks.org/css-speak-property/)

`speak` 属性用于定义文本是否应该以听觉方式呈现。

## 语法

```html
speak: auto | normal | spell-out | none 
        | never | always| initial | inherit;
```

## 参数

该属性接受上述六个参数，如下所述:

*   **Automatic:** 此参数告诉浏览器运行正常，这意味着如果 `display` 属性没有被阻止，它将是可见的并被大声朗读。
*   **Normal:** 此参数告诉浏览器根据父级和子级元素遵循本地语言的发音。
*   **Spelling:** 此参数用于逐个拼写后续文本。
*   **Never:** 此参数阻止元素被听觉渲染。
*   **Always:** 此参数使元素始终被听觉渲染。
*   **None:** 此参数用于停止渲染时间，可以无时间使用。

## 示例 1

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .number {
            speak: none;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>

    <p>CSS speak Property</p>

    <ol class="number">
        <li>One</li>
        <li>Two</li>
        <li>Three</li>
        <li>Four</li>
    </ol>
</body>

</html>
```