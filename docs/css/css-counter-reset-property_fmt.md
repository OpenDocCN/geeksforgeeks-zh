# CSS 计数器复位属性

> 原文: [https://www.geeksforgeeks.org/css-counter-reset-property/](https://www.geeksforgeeks.org/css-counter-reset-property/)

CSS 中的计数器重置属性用于为元素创建或重置 CSS 计数器。此属性与 `counter-increment` 属性和 `content` 属性一起工作。

## 语法

```html
counter-reset = none|name number|initial|inherit;
```

## 默认值

*   `none`

## 属性值

*   `none`: 为默认值。该值不会重置计数器。
*   `name number`: 元素每次出现时重置计数器的值。如果未指定，默认值为 0。
*   `initial`: 将计数器复位属性设置为默认值。
*   `inherit`: 元素从其父元素继承属性。

## 示例 1

本示例使用计数器重置属性创建部分。

### HTML

```html
<!DOCTYPE html>
<html>

<head>

<!-- CSS property to set counter-reset property -->
    <style>

/* set chapter counter to 0*/
        body {
            counter-reset: chapter;    
        }
        .chapter:before {
            content: counter(chapter) ". ";
            display: inline;
        }
        .chapter {

/* Increment the chapter counter by 1,
            same as counter-increment: chapter 1; */
            counter-increment: chapter;

/* set section counter to 0 */
            counter-reset: section;    
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

<div class = "chapter">HTML</div>
    <div class = "chapter">CSS</div>
    <div class = "chapter">PHP</div>
</body>

</html>
```

**输出:**

![](img/47b78217526c4f0a45bb97e0a0ba045c.png)

## 示例 2

本示例使用计数器重置属性创建节和子节。

### HTML

```html
<!DOCTYPE html>
<html>

<head>

<!-- CSS style to create counter-reset property -->
    <style>
        body {
            counter-reset: section;
        }
        h1 {
            counter-reset: category;
        }
        h1:before {
            counter-increment: section;
            content: "Section " counter(section) ". ";
        }
        h3:before {
            counter-increment: category;
            content: counter(section) "." counter(category) " ";
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

<h3>HTML</h3>
    <h3>CSS </h3>

<h1>References</h1>

<h3>HTML Tags</h3>
    <h3>CSS Properties</h3>
</body>

</html>
```

**输出:**

![](img/83705d6209b9aec16e5c222483dc5daf.png)

## 支持的浏览器

`counter-reset` 属性支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 8.0
*   Firefox 2.0
*   Safari 3.1
*   歌剧 9.6