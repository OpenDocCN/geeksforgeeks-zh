# CSS scroll-padding-left 属性

> 原文：[https://www.geeksforgeeks.org/css-scroll-padding-left-property/](https://www.geeksforgeeks.org/css-scroll-padding-left-property/)

`scroll-padding-left` 属性用于一次性设置滚动容器或元素左侧的所有填充。为 `scroll-padding-left` 指定的值决定了在快照对齐之外，页面应该保持多少可见。

## 语法

```html
scroll-padding-left: length_values
```

或者

```html
scroll-padding-left: keyword_values
```

或者

```html
scroll-padding-left: global_values
```

## 属性值

该属性接受上面提到的和下面描述的三个属性值。

*   **length_values:** 该属性是指用长度单位定义的值。例如：`px`、`em`、`vh`、`%` 等。
*   **keyword_values:** 该属性是指关键字值，例如用 `auto` 定义的值。一般来说，默认情况下这将设置为 `0px`，但如果非零值更合适，它也可以是非零值。
*   **global_values:** 该属性是指 `inherit`、`initial`、`unset` 等全局值。

## 示例

以下示例说明了 `scroll-padding-left` 属性。

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            width: 275px;
            height: 300px;
            border: 2px solid red;
            scroll-snap-align: none start;
        }

        .GeeksforGeeks {
            width: 300px;
            height: 300px;
            border: 2px solid green;
            text-align: center;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
        }
    </style>
</head>

<body>
    <div class="GeeksforGeeks" style="scroll-padding-left: 80px;">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geek">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" class="geek">
    </div>
</body>

</html>
```

### 输出

![](img/126b233a9d7a7b43e4029e5a2ca9119d.png)

## 支持的浏览器

*   Chrome
*   Firefox
*   Opera
*   Edge
*   Safari (部分支持)
*   Internet Explorer (不支持)