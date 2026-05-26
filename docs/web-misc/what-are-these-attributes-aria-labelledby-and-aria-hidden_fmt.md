# 这些属性‘aria-labelledby’和‘aria-hidden’是什么？

> 原文: [https://www.geeksforgeeks.org/what-are-these-attributes-aria-labelledby-and-aria-hidden/](https://www.geeksforgeeks.org/what-are-these-attributes-aria-labelledby-and-aria-hidden/)

术语 **ARIA** 具有诸如`aria-labelledby`和`aria-hidden`的属性，代表可访问的丰富互联网应用。这些是一套标准和指导方针，使网络应用程序更容易被残疾人访问。这用于 HTML 文档中的交互式内容，如错误消息、进度条、渐进式提示等。

有多种 ARIA 属性，如下所示：

*   `aria-autocomplete`
*   `aria-checked`
*   `aria-disabled`
*   `aria-expanded`
*   `aria-hidden`
*   `aria-invalid`

## ARIA-hidden

`ARIA-hidden:` ARIA 属性 `aria-hidden` 用于指示辅助技术，如屏幕阅读器，它向残疾人指示文档上的内容，具有该属性的内容实际上可以跳过。屏幕阅读器将跳过元素内容而不口述它们。

### 什么类型的内容应该有一个 `aria-hidden` 属性？

没有重大意义的内容可以跳过。此类内容的示例包括以下内容。

*   纯表象内容
*   占位符内容
*   特定于基于浏览器的用户环境的内容

### 区别 `aria-hidden` 和 HTML 的原生 `hidden` 属性

*   **HTML `hidden` 属性:** 这个用来表示网页浏览器不应该呈现内容。
*   **`aria-hidden` 属性:** 这个用来表示像屏幕阅读器这样的辅助技术可以跳过这个属性的内容。

### 示例

```html
<!DOCTYPE html>
<html>

<body>
    <h2>Welcome To GFG</h2>

    <p aria-hidden="true">
        This content will be
        skipped by Screen-Readers
    </p>

</body>

</html>
```

**输出:**

“p”元素内容是非交互内容，因此这些内容对屏幕阅读器是隐藏的。

### 关于 `aria-hidden` 的关键要知道的事情

*   `aria-hidden` 不能被可聚焦元素使用。
*   `aria-hidden` 会将其所有子元素标记为隐藏。无法用 `aria-hidden="false"` 设置子元素并使其可见。

## aria-labelledby

`aria-labelledby:` `aria-labelledby`属性用于关联标签和包含标签文本的元素。`aria-labelledby` 的值通常是包含标签文本的元素的 ID。它的值部分可以有多个元素 id。这非常类似于包含`for`属性的输入元素来链接标签。

### 示例

```html
<!DOCTYPE html>
<html>

<body>
    <h2>Welcome To GFG</h2>
    <div id="myBillingId">Billing</div>

    <div>
        <div id="myFirstName">First Name</div>
        <input type="text"
            aria-labelledby="myFirstName" />
    </div>

    <div>
        <div id="myContactNumber">
            Contact Number
        </div>
        <input type="text" aria-labelledby
            ="myFirstName myContactNumber" />
    </div>
</body>

</html>
```

## 什么时候使用 HTML 规范属性和 ARIA 属性？

ARIA 规范也是为残疾人设计的内容。在某些情况下使用 HTML 规范属性可能是有意义的，在某些情况下使用 ARIA 规范可能是有意义的，这必须针对目标受众来处理。