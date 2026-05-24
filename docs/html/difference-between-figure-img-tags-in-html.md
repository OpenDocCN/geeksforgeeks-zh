# HTML 中

<figure>& 标签的区别</figure>

> 原文:[https://www . geesforgeks . org/figure-img-tags-in-html/](https://www.geeksforgeeks.org/difference-between-figure-img-tags-in-html/)

在本文中，我们将了解

<figure>& 标签及其实现。我们也将了解它们之间的差异。让我们从 HTML 中的图形标签开始讨论。</figure>

[**HTML <图>标记**](https://www.geeksforgeeks.org/html5-figure-tag/)**:**HTML 5 中的 [<图>标记](https://www.geeksforgeeks.org/html5-figure-tag/)用于添加独立的内容，如文档中的插图、图表、照片或代码列表。它与主流程相关，但它可以在文档的任何位置使用，并且图形与文档的流程一致，如果将其删除，则不应影响文档的流程。简而言之，图形标签用于在语义上组织图像、视频、音频甚至图表或表格的内容，以及 HTML 文档中的代码块。

**语法:**

```html
<figure>
    <img src="url">
    <figcaption>content</figcaption>
</figure>
```

**属性:**主要包含两个标签，如下所示:

*   [**img src**](https://www.geeksforgeeks.org/html-img-src-attribute/) **:** 此标签用于在文档中添加图像源。
*   [**fig caption**](https://www.geeksforgeeks.org/html5-figcaption-tag/)**:**此标签用于设置图像的字幕。可以选择使用。

**示例:**该示例说明了<图形>标签以及 src、宽度、高度& alt 属性的使用。

## 超文本标记语言

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

**输出:**在这种情况下，<图>标签，它已经做了所有的改变，因为带有标题的图像被适当地对齐，与空白区有一些距离。图像和标题是彼此的一部分。边界被添加到<图形>标签和<图形标题>标签，两者都占据了边界。<图>标记是内联元素。

![](img/80c5dce95349dabad81ba6af7f371aca.png)

<figure>标签</figure>

[**HTML<img>Tag:**](https://www.geeksforgeeks.org/html-img-tag/)**HTML[**<img>**Tag](https://www.geeksforgeeks.org/html-img-tag/#:~:text=HTML%20tag%20is%20used,holds%20space%20for%20the%20image.&text=Attributes%3A%20The%20tag,the%20path%20to%20the%20image.)用于在网页/网站中添加图片或设置背景。现在的网站不直接在网页上添加图像，因为图像是通过使用< img >标签链接到网页上的，该标签为图像保留空间。**

****语法:****

```html
<img src="url" alt="some_text">
```

****属性:**包含以下属性值:**

*   ****src:** 用于指定源图像的 URL 路径。**
*   ****alt:** 用于在图像因某种原因无法显示时，为图像指定替代文本。**

****示例:**在本例中，我们使用了< img >标签以及 src、宽度、高度和 alt 属性。**

## **超文本标记语言**

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

****输出:**在< img >标签的情况下，它没有正确对齐并且非常接近边距，并且标题远离图像。图像和标题不是彼此的一部分。边框不是图像和标题的一部分。< img >标签是一个内嵌元素，但是当我们指定宽度和高度时，它就变成了一个块元素。**

**![Image tag](img/14bc2724a41839ebe132e5f311be3fa1.png)

标签** 

****图<图>图&图< img >标签:****

<figure class="table">**1。

| 

#### S 号

 | 

#### Figure < Figure > Label

 | 

#### 【T98】【img】>-什么

 |
| --- | --- | --- |
| Graphics tags are used to semantically organize the contents of images, videos, audio and even charts or tables and code blocks in HTML documents. | Image tags are used to add images to HTML pages. < img > Tags can only be inserted into images. |
| 2。 | The tag is a container tag. | < img > tag is an empty tag. |
| 3。 | This tag provides a container for the content, which is equivalent to a graph or chart in the book. | HTML 【T0] tag is used to embed images into HTML documents. |
| 4。 | This tag is an inline element. | It is an embedded element, but when we specify the width and height, it becomes a block element. |
| 5。 | You can use the fig caption element in combination with the fig caption element to provide a title for the content of your figcaption element. | There is no special title tag in the image tag, so we can use < p > tag or < span > tag to add false title. |
| 6。 | Make the code easy for the machine to understand. Easy access to search engines. | Machines are hard to understand. |
| 7。 | The element itself may contain many other sub-elements, such as code block, image, audio, video, etc. |  There cannot be multiple elements inside the tag, only images can be added in the < img > tag. |
| 8。 | Graphic labels contain default alignment and styles. | Image labels do not contain any default alignment and styles. |** </figure>