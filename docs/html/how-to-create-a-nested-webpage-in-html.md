# 如何在 HTML 中创建嵌套网页？

> 原文:[https://www . geesforgeks . org/如何在 html 中创建嵌套网页/](https://www.geeksforgeeks.org/how-to-create-a-nested-webpage-in-html/)

当一个完全不同的网页的内容嵌入到另一个网页时，它被称为嵌套网页。简而言之，一个网页位于另一个完全不同领域的网页内。

在本文中，我们将学习如何创建嵌套网页。创建嵌套网页有两种方法。它们如下。

1.  使用<iframe>标签</iframe>
2.  使用<embed>标签

**1。使用< iframe >标签:**

HTML 中的 [iframe](https://www.geeksforgeeks.org/html-iframes/) 代表内嵌框架。“iframe”标签在文档中定义了一个矩形区域，浏览器可以在其中显示单独的文档，包括滚动条和边框。内嵌框架用于在当前 HTML 文档中嵌入另一个文档

**语法:**

```html
<iframe src="URL"></iframe>
```

可以以直列框架的*高度*和*宽度*为属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
   <head></head>
   <body>
      <h1>
        Creating a Nested Webpage using 
        'iframe' Tag: Geeksforgeeks
      </h1>

      <iframe src="https://www.geeksforgeeks.org" 
              height="500px" width="1000px">
      </iframe>
   </body>
</html>
```

**输出:**

![](img/ca867149e088a6f14eb1ac4199bdcd1c.png)

[**2。使用<嵌入>标签:**T3】](https://www.geeksforgeeks.org/html-embed-tag/)

HTML 中的<embed>标记用于将外部应用程序嵌入到 HTML 文档中，这些外部应用程序通常是音频或视频等多媒体内容。但是可以使用这个标签嵌入另一个原始的 HTML 内容。我们可以使用这个功能来创建嵌套网页。

**语法:**

```html
<embed src="URL" type="text/html" /> 
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
   <head></head>
   <body>
      <h1>
        Creating a Nested Webpage using
        'embed' Tag: Geeksforgeeks
      </h1>

      <embed src="https://www.geeksforgeeks.org" 
          type="text/html" />
   </body>
</html>
```

**输出:**

![](img/183ecbffaea9a7b50545c471c951b95c.png)

由于版权问题，该网站可能会阻止您嵌入其内容。因此，在将另一个网页用作网站内的嵌套网页之前，必须获得适当的许可和授权。