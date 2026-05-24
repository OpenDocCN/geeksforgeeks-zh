# CSS scroll-snap-align 属性

> 原文：[https://www.geeksforgeeks.org/css-scroll-snap-align-property/](https://www.geeksforgeeks.org/css-scroll-snap-align-property/)

CSS `scroll-snap-align` 属性表示元素或容器的对齐端口内的框的对齐区域的对齐位置。

## 语法

```html
scroll-snap-align: Keyword_Values;
/* Or */
scroll-snap-align: Global_Values;
```

## 属性值

`scroll-snap-align` 属性接受上面提到的和下面描述的两个值：

*   **关键字值：** 该属性指的是 `none`、`start`、`end`、`center` 等关键字值。
*   **全局值：** 该属性是指 `inherit`、`initial`、`unset` 等全局值。

**注意：** 当设置了两个属性值时，那么第一个用于块，第二个用于内联。例如 `scroll-snap-align: start end;`

## 示例 1

在此示例中，您可以通过滚动到示例内容的两个“界面”中间的一点来查看 `scroll-snap-align` 的效果。这里我们使用了 `none start` 作为属性值。

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .geeks {
            width: 255px;
            height: 300px;
            border: 4px solid greenyellow;
            scroll-snap-align: none start;
        }
        .Container {
            width: 300px;
            height: 300px;
            border: 5px solid red;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
            scroll-snap-type: x mandatory;
            scroll-snap-stop: always;
        }
    </style>
</head>
<body>
    <div class="Container">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geeks">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131449/img5.jpeg" class="geeks">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131452/img4-300x167.png" class="geeks">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200723131450/img6-300x82.png" class="geeks">
    </div>
</body>
</html>
```

## 输出

![](img/69428d86bc74ff40f5fafd2510875655.png)

## 支持的浏览器

*   Chrome
*   Firefox
*   Safari
*   Edge
*   Opera
*   Internet Explorer（不支持）