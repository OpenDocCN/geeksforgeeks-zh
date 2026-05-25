
# HTML

## Tag

> 原文: [https://www.geeksforgeeks.org/html-li-tag/](https://www.geeksforgeeks.org/html-li-tag/)

HTML 中的 `<li>` 标签用于定义列表项。它用于 [有序列表](https://www.geeksforgeeks.org/html-ol-tag/) 或 [无序列表](https://www.geeksforgeeks.org/html-ul-tag/)。`<li>` 标签需要一个开始标签和一个结束标签。

**注意：** 如果列表项后面跟着另一个 `<li>` 元素，或者如果其父元素中没有更多内容，则可以省略结束标签。

## 语法

```html
<li> List Items </li>
```

## 属性值

[**值:**](https://www.geeksforgeeks.org/html-li-value-attribute/) 值属性用于指定列表项的起始编号。列表项从这个数字开始，并随着每增加一项而增加其值。值属性仅适用于有序列表，即 `<ol>` 标签。

## 示例 1

本示例在有序列表中使用 `<li>` 标签。

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

<h2>HTML li Tag</h2>

<ol>
        <li>Geeks</li>
        <li>Sudo</li>
        <li>Gfg</li>
        <li>Gate</li>
        <li>Placement</li>
    </ol>
</body>

</html>
```

## 示例 2

本示例使用带有无序列表的 `<li>` 标签。

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

<h2>HTML li Tag</h2>

<ul>
        <li>Geeks</li>
        <li>Sudo</li>
        <li>Gfg</li>
        <li>Gate</li>
        <li>Placement</li>
    </ul>
</body>

</html>
```

## 示例 3

本示例使用带有值属性的 `<li>` 标记来创建列表。

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

<h2>HTML li Tag</h2>

<ol>
        <li value="5">Geeks</li>
        <li>Sudo</li>
        <li>Gfg</li>
        <li>Gate</li>
        <li>Placement</li>
    </ol>
</body>

</html>
```

## 将样式应用于 `<li>` 标签

一些 CSS 属性也可以用来设置 `<li>` 元素的样式，这些属性包括：[列表样式](https://www.geeksforgeeks.org/css-list-style-property/)、[列表样式图像](https://www.geeksforgeeks.org/css-list-style-image-property/)、[列表样式位置](https://www.geeksforgeeks.org/css-list-style-position-property/)和[列表样式类型](https://www.geeksforgeeks.org/css-list-style-type-property/)。这些属性可以直接应用于 `<li>` 元素，尽管它们通常应用于父元素。

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队
