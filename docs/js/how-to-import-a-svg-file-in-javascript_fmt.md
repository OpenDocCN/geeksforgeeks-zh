# 如何在 JavaScript 中导入一个 SVG 文件？

> 原文：[https://www.geeksforgeeks.org/how-to-import-a-svg-file-in-javascript/](https://www.geeksforgeeks.org/how-to-import-a-svg-file-in-javascript/)

在本文中，我们将看到并使用不同的使用 SVGs（可伸缩矢量图形）的方法。

## 方法一：使用 HTML `<img>` 元素

最快的方法。

### 语法

```
<img src='logo.svg' alt="some file" height='100' width='100' style="color:green;"/>
```

通过 `<img>` 元素嵌入一个 SVG，您需要：

*   `src` 属性
*   `height` 属性（如果您的 SVG 没有固有的长宽比）
*   `width` 属性（如果您的 SVG 没有固有的长宽比）

### 优点

*   简单快速的实现。
*   通过嵌套 & 缓存 SVG 文件，因此减少了加载时间。

### 缺点

*   无法操作 SVG 文件。
*   您只能使用内嵌 CSS 来设置 SVG 的样式。
*   无法使用 CSS 伪类来设置 SVG 的样式。

### 示例

```html
<!DOCTYPE html>
<html lang="en">
  <body>
    <img
      src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210205161739/Screenshot-2021-02-05-161721.png"
      alt="gfg-logo"
      height="100"
      width="100"
      style="background-color: green"
    />
  </body>
</html>
```

### 输出

![](img/724a01926e02c9842dde0e61a8dc44cb.png)

使用 HTML `<img>` 元素的 SVG 文件

## 方法二：使用 SVG 作为 `<object>`

### 语法

```
<object type="image/svg+xml" data="logo.svg" class="logo">
  Logo
</object>
```

通过 `<object>` 元素嵌入 SVG 需要：

*   `type` 属性
*   `data` 属性
*   `class` 属性（如果使用外部/内部 CSS）

### 优点

*   可以使用外部/内部 CSS 来设置 SVG 的样式。
*   简单快速的实现。
*   将非常适合缓存。

### 缺点

*   要使用外部样式表，需要在 SVG 文件中使用。
*   不太熟悉语法和实现。

### HTML 代码

```html
<!DOCTYPE html>
<html lang="en">
<body>
  <object type="image/svg+xml"
          data="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210205161739/Screenshot-2021-02-05-161721.png"
          class="logo">
    GFG Logo
  </object>
</body>
</html>
```

### CSS 代码

以下是上述代码中使用的 `styles.css` 文件的内容。

```css
.logo {
  height: 100;
  width: 100;
}
```

### 输出

![](img/724a01926e02c9842dde0e61a8dc44cb.png)

使用 HTML `<object>` 元素的 SVG 文件

## 方法三：用 `<iframe>` 嵌入一个 SVG

### 语法

```
<iframe src="logo.svg" width="500" height="500">
</iframe>
```

通过 `<iframe>` 元素嵌入一个 SVG 需要：

*   `src` 属性
*   `height` 属性（如果您的 SVG 没有固有的纵横比）
*   `width` 属性（如果您的 SVG 没有固有的纵横比）

### 优点

*   快速简单的实施。
*   与 `<object>` 元素相同。

### 缺点

*   你不能用 JavaScript 来操作 SVG。
*   缓存不是很好。

### HTML 代码

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <iframe
      src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210205161739/Screenshot-2021-02-05-161721.png"
      width="150"
      height="150">
    </iframe>
  </body>
</html>
```

### 输出

![](img/566f0c3f3e64f1da8447be1c1f894de0.png)