# CSS scroll-padding-right 属性

> 原文: [https://www.geeksforgeeks.org/css-scroll-padding-right-property/](https://www.geeksforgeeks.org/css-scroll-padding-right-property/)

`scroll-padding-right` 属性用于一次性设置滚动容器或元素右侧的所有填充。为 `scroll-padding-right` 指定的值决定了主要位于对齐滚动之外的页面应该保持可见的程度。

### 语法:

```html
scroll-padding-right: keyword_values
```

或者

```html
scroll-padding-right: length_values
```

或者

```html
scroll-padding-right: global_values
```

### 属性值:

该属性接受上面提到的和下面描述的三个属性。

*   **length_values:** 该属性是指用长度单位定义的值: `px`，`em`，`vh`，`%` 等。
*   **keyword_values:** 该属性是指 `keyword_values`，用 `auto` 等单位定义。一般来说，默认情况下这将被设置为 `0px`，但如果非零值更合适，它也可以是非零值。
*   **global_values:** 该属性是指 `inherit`、`initial`、`unset` 等全局值。

### 示例:

以下示例说明了 `scroll-padding-right` 属性。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            width: 300px;
            height: 275px;
            border: 2px solid black;
            scroll-snap-align: none end;
        }

        .GeeksforGeeks {
            width: 300px;
            height: 300px;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
        }
    </style>
</head>

<body>
    <div class="GeeksforGeeks" style="scroll-padding-right: 90px;">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geek">
    </div>
</body>

</html>
```

### 输出:

![](img/268af6f149a549ef3a7e47b5253cb373.png)

### 支持的浏览器:

*   `Chrome`
*   `Firefox`
*   `Edge`
*   `Opera`
*   `Safari` (部分支持)
*   `Internet Explorer` (不支持)