# 如何去除内嵌块元素之间的空间？

> 原文：`https://www.geeksforgeeks.org/how-to-remove-the-space-between-inline-block-elements/`

有两种方法可以删除内联块元素之间的空间。

## 方法 1：设置父元素字体大小为 0

将内嵌块元素的父元素的字体大小指定为 `0px`，然后将适当的字体大小指定给内嵌块元素。

> **语法：**
> ```css
> 父元素 {
>   font-size: 0px;
> }
> 父元素子元素 {
>   display: inline-block;
>   font-size: 必选字号;
> }
> ```

以下代码说明了上述概念：

### 示例代码

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Assign font-size of parent element to 0px */
        div {
            font-size: 0px;
        }

        /* Making the element inline-block */
        /* Assign proper font-size to the inline block element */
        div span {
            display: inline-block;
            background-color: green;
            font-size: 10rem;
        }
    </style>
    <title>How to remove spaces between inline block elements</title>
</head>

<body>
    <div>
        <span>Geeks</span>
        <span>For</span>
        <span>Geeks</span>
    </div>
</body>

</html>
```

**输出：**

![](img/2a28bfc584e7cf06e1f0ac76a6582fd4.png)

## 方法 2：使用 Flex 布局

使父元素的 `display` 属性为 `flex`。

> **语法：**
> ```css
> 父元素 {
>   display: flex;
> }
> 父元素子元素 {
>   display: inline-block;
>   font-size: 必选字号;
> }
> ```

### 示例代码

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Making the parent element a flexbox */
        div {
            display: flex;
        }

        /* Making the element inline-block */
        /* Assign proper font-size to the inline block element */
        div span {
            display: inline-block;
            background-color: rgb(53, 77, 5);
            font-size: 10rem;
        }
    </style>
    <title>How to remove spaces between inline block elements</title>
</head>

<body>
    <div>
        <span>Geeks</span>
        <span>For</span>
        <span>Geeks</span>
    </div>
</body>

</html>
```

**输出：**

![](img/0341327be59afbdf3329e0697443ce2d.png)