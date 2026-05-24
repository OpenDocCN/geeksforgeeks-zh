# CSS scroll-padding-inline 属性

> 原文：[https://www.geeksforgeeks.org/css-scroll-padding-inline-property/](https://www.geeksforgeeks.org/css-scroll-padding-inline-property/)

`scroll-padding-inline` 属性用于一次性将所有滚动填充设置到内联维度中滚动元素或容器的开始和结束。该属性是 `scroll-padding-inline-start` 和 `scroll-padding-inline-end` 属性的简写。

开始侧和结束侧的选择取决于写入模式。对于 `horizontal-tb` 写入模式，开始侧和结束侧分别是左侧和右侧。同样，对于 `vertical-rl` 或 `vertical-lr` 书写模式，开始侧和结束侧分别是顶侧和底侧，其中 `horizontal-tb` 代表水平从上到下，`vertical-rl` 是从右到左的垂直，而 `vertical-lr` 是从左到右的垂直。

## 语法

```html
scroll-padding-block-end: keyword_values
```

或者

```html
scroll-padding-block-end: length_values
```

或者

```html
scroll-padding-block-end: global_values
```

## 属性值

该属性接受上面提到的和下面描述的三个属性。

*   `length_values`：该属性是指用长度单位定义的值。例：`px`、`em`、`vh`、`%` 等。
*   `keyword_values`：该属性是指用 `auto` 等单位定义的关键字值。一般来说，默认情况下这将被设置为 `0px`，但如果非零值更合适，它也可以是非零值。
*   `global_values`：该属性是指 `inherit`、`initial`、`unset` 等全局值。

## 示例

在本例中，您可以通过滚动到示例内容的两个“界面”中间的点来查看 `scroll-padding-inline` 的效果。

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .img {
            width: 275px;
            height: 300px;
            scroll-snap-align: none start;
        }

        .GeeksforGeeks {
            width: 300px;
            height: 300px;
            border: 2px solid red;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
        }
    </style>
</head>

<body>

<div class="GeeksforGeeks" style="scroll-padding-inline: 100px;">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" class="img">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="img">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" class="img">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="img">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" class="img">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" class="img">
</div>
</body>

</html>
```

### 输出

![](img/38f4390f6a4df5fb7b813bdd433d1b61.png)

## 支持的浏览器

*   Firefox
*   Chrome
*   Edge
*   Opera
*   Safari（不支持）
*   Internet Explorer（不支持）