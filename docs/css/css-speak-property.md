# CSS 说话属性

> 原文:[https://www.geeksforgeeks.org/css-speak-property/](https://www.geeksforgeeks.org/css-speak-property/)

**CSS speak 属性**用于定义文本是否应该以听觉方式呈现。

**语法:**

```html
speak: auto | normal | spell-out | none 
        | never | always| initial | inherit;

```

**参数:**该属性接受上述六个参数，如下所述:

*   **Automatic: This parameter tells** that the browser is running normally, which means that if the display attribute is not blocked, it will be visible and read audibly.
*   **Normal: this parameter tells** the browser to follow the pronunciation of local language according to parent-child elements.
*   **Spelling:** This parameter is used to define the spelling of the following text one at a time.
*   **Never:** This parameter prevents the element from being rendered audibly.
*   **Always:** This parameter makes the element always render audibly.
*   **None:** This parameter is used to stop the rendering time and can be used without time.

**示例 1:**

## HTML

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