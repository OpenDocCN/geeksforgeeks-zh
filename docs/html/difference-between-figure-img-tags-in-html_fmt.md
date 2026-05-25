# HTML 中 `<figure>` & `<img>` 标签的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-figure-img-tags-in-html/](https://www.geeksforgeeks.org/difference-between-figure-img-tags-in-html/)

在本文中，我们将了解 `<figure>` & `<img>` 标签及其实现。我们也将了解它们之间的差异。让我们从 HTML 中的 `<figure>` 标签开始讨论。

## HTML `<figure>` 标记

HTML 5 中的 [`<figure>` 标记](https://www.geeksforgeeks.org/html5-figure-tag/)用于添加独立的内容，如文档中的插图、图表、照片或代码列表。它与主流程相关，但它可以在文档的任何位置使用，并且图形与文档的流程一致，如果将其删除，则不应影响文档的流程。简而言之，`<figure>` 标签用于在语义上组织图像、视频、音频甚至图表或表格的内容，以及 HTML 文档中的代码块。

**语法:**

```html
<figure>
    <img src="url">
    <figcaption>content</figcaption>
</figure>
```

**属性:** 主要包含两个标签，如下所示:

*   [`img src`](https://www.geeksforgeeks.org/html-img-src-attribute/): 此标签用于在文档中添加图像源。
*   [`figcaption`](https://www.geeksforgeeks.org/html5-figcaption-tag/): 此标签用于设置图像的字幕。可以选择使用。

**示例:** 该示例说明了 `<figure>` 标签以及 `src`、`width`、`height` & `alt` 属性的使用。

### HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      figure {
        border: 2px solid black;
        padding: 5px;
      }
    </style>
  </head>

  <body>
    <figure>
      <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210827151326/gfg-200x200.png"
        alt="image"
        width="200px"
        height="200px"/>
      <figcaption>Geeks For Geeks</figcaption>
    </figure>
  </body>
</html>
```

**输出:** 在这种情况下，`<figure>` 标签，它已经做了所有的改变，因为带有标题的图像被适当地对齐，与空白区有一些距离。图像和标题是彼此的一部分。边界被添加到 `<figure>` 标签和 `<figcaption>` 标签，两者都占据了边界。`<figure>` 标记是内联元素。

![](img/80c5dce95349dabad81ba6af7f371aca.png)

## HTML `<img>` Tag

HTML [`<img>` Tag](https://www.geeksforgeeks.org/html-img-tag/)用于在网页/网站中添加图片或设置背景。现在的网站不直接在网页上添加图像，因为图像是通过使用 `<img>` 标签链接到网页上的，该标签为图像保留空间。

**语法:**

```html
<img src="url" alt="some_text">
```

**属性:** 包含以下属性值:

*   `src`: 用于指定源图像的 URL 路径。
*   `alt`: 用于在图像因某种原因无法显示时，为图像指定替代文本。

**示例:** 在本例中，我们使用了 `<img>` 标签以及 `src`、`width`、`height` 和 `alt` 属性。

### HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible"
          content="IE=edge" />
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      img {
        border: 2px solid black;
        padding: 5px;
      }
    </style>
  </head>
  <body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210827151326/gfg-200x200.png"
      alt="image"
      width="200px"
      height="200px"/>

<p>Geeks For Geeks</p>

  </body>
</html>
```

**输出:** 在 `<img>` 标签的情况下，它没有正确对齐并且非常接近边距，并且标题远离图像。图像和标题不是彼此的一部分。边框不是图像和标题的一部分。`<img>` 标签是一个内嵌元素，但是当我们指定宽度和高度时，它就变成了一个块元素。

![](img/14bc2724a41839ebe132e5f311be3fa1.png)

## `<figure>` & `<img>` 标签:

| 序号 | `<figure>` 标签 | `<img>` 标签 |
| :--- | :--- | :--- |
| 1. | 图形标签用于在语义上组织 HTML 文档中的图像、视频、音频、图表或表格以及代码块等内容。 | 图像标签用于向 HTML 页面添加图像。`<img>` 标签只能插入图像。 |
| 2. | `<figure>` 标签是一个容器标签。 | `<img>` 标签是一个空标签。 |
| 3. | 此标签为内容提供一个容器，相当于书中的图形或图表。 | HTML `<img>` 标签用于将图像嵌入 HTML 文档。 |
| 4. | 此标签是一个内联元素。 | 它是一个内嵌元素，但当我们指定宽度和高度时，它就变成了一个块元素。 |
| 5. | 您可以将 `<figcaption>` 元素与 `<figure>` 元素结合使用，为 `<figure>` 元素的内容提供标题。 | 图像标签中没有特殊的标题标签，因此我们可以使用 `<p>` 标签或 `<span>` 标签来添加伪标题。 |
| 6. | 使机器易于理解代码。易于被搜索引擎访问。 | 机器难以理解。 |
| 7. | 元素本身可以包含许多其他子元素，例如代码块、图像、音频、视频等。 | `<img>` 标签内不能有多个元素，只能添加图像。 |
| 8. | 图形标签包含默认的对齐方式和样式。 | 图像标签不包含任何默认的对齐方式和样式。 |