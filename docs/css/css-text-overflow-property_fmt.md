# CSS 文本溢出属性

> 原文：[https://www.geeksforgeeks.org/css-text-overflow-property/](https://www.geeksforgeeks.org/css-text-overflow-property/)

CSS 中的 `text-overflow` 属性用于指定某些文本已经溢出并隐藏在视图之外。[`white-space`](https://www.geeksforgeeks.org/css-white-space-property/) 属性必须设置为 `nowrap`，而 `overflow` 属性必须设置为 `hidden`。溢出的内容可以被剪裁，显示省略号(“…”)或显示自定义字符串。

**语法：**

```html
text-overflow: clip|string|ellipsis|initial|inherit;
```

**属性值：** 下面的例子很好地描述了所有的属性。

## `clip`

文字被剪裁，看不到。这是默认值。

**语法：**

```html
text-overflow: clip;
```

**示例：** 本示例说明了 `text-overflow` 属性的使用，该属性的值被设置为 `clip`。

### HTML 代码

```html
<html>
<head>
    <title> CSS | text-overflow Property </title>
    <style type="text/css">
    div {
        width: 500px;
        font-size: 50px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: clip;
    }
    </style>
</head>

<body>
    <div>GeeksforGeeks: A computer science portal for geeks.</div>
</body>
</html>
```

**输出：**

![](img/6aaad8697648327611de1cb71f94f938.png)

CSS 文本溢出剪辑

## `ellipsis`

文本被剪裁，剪裁后的文本表示为 `“…”`。

**语法：**

```html
text-overflow: ellipsis;
```

**示例：** 本示例说明了 `text-overflow` 属性的使用，该属性的值被设置为 `ellipsis`。

### HTML 代码

```html
<html>
<head>
    <title> CSS | text-overflow Property </title>
    <style type="text/css">
    div {
        width: 500px;
        font-size: 50px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }
    </style>
</head>

<body>
    <div> GeeksforGeeks: A computer science portal for geeks. </div>
</body>
</html>
```

**输出：**

![](img/76e165ac49f1d922a7198003ff371d06.png)

## `string`

使用编码器选择的字符串向用户表示剪切的文本。此选项仅在火狐浏览器中可见。

**语法：**

```html
text-overflow: string;
```

其中字符串由开发人员定义。

**示例：** 本示例说明了 `text-overflow` 属性的使用，该属性的值被设置为特定的字符串值。

### HTML 代码

```html
<html>
<head>
    <title> CSS | text-overflow Property </title>
    <style type="text/css">
    div {
        width: 500px;
        font-size: 50px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: " ";
    }
    </style>
</head>

<body>
    <div> GeeksforGeeks: A computer science portal for geeks. </div>
</body>
</html>
```

**输出：**

![](img/6b503e2b93d26af41e4bf9ac09dcd98d.png)

## `initial`

用于将元素的 CSS 属性设置为默认值，即该值会将 `text-overflow` 属性设置为默认值。

**语法：**

```html
text-overflow: initial;
```

**示例：** 本示例说明了 `text-overflow` 属性的使用，该属性的值设置为 `initial`。

### HTML 代码

```html
<html>
<head>
    <title> CSS | text-overflow Property </title>
    <style type="text/css">
    div {
        width: 500px;
        font-size: 50px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: initial;
    }
    </style>
</head>

<body>
    <div> GeeksforGeeks : A computer science portal for geeks. </div>
</body>
</html>
```

**输出：**

![](img/9eba20f0bf9d6e91c431d4ff3a1340b4.png)

## `inherit`

用于从元素的父元素属性值继承元素的属性，即该值会将 `text-overflow` 属性设置为父元素的值。

**语法：**

```html
text-overflow: inherit;
```

**示例：** 该示例说明了 `text-overflow` 属性的使用，该属性的值被设置为 `inherit`。

### HTML 代码

```html
<html>
<head>
    <title> CSS | text-overflow Property </title>
    <style type="text/css">
    div {
        width: 500px;
        font-size: 50px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    h3 {
        width: 500px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: inherit;
    }
    </style>
</head>

<body>
    <div> GeeksforGeeks: A computer science portal for geeks.
        <h3>
         I have inherited my overflow property from div.
        </h3>
    </div>
</body>
</html>
```

**输出：**

![](img/8f9e73746ff9e0999843e827cf7e1e29.png)

**支持的浏览器：** `text-overflow` 属性支持的浏览器如下：

*   Chrome 1.0
*   Firefox 7.0
*   Microsoft Edge 12.0
*   IE 6.0
*   Safari 1.3
*   Opera 11.0