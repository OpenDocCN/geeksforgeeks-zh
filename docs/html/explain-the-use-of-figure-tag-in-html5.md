# 解释 HTML5 中图形标签的使用

> 原文:[https://www . geesforgeks . org/explain-the-of-of-figure-tag-in-html 5/](https://www.geeksforgeeks.org/explain-the-use-of-figure-tag-in-html5/)

在 HTML 中，

<figure>标签用于在文档中包含独立的信息，如插图、图表、照片或代码列表。它链接到主流，但它可以在文档的任何地方使用，图形与内容一起流动，因此删除它不应影响文档的流动。为此，HTML5 包含了一个新的标签。因为

<figure>元素是一个切片根，所以其内容的轮廓从页面的主轮廓中移除。</figure>

</figure>

**使用图形标签:**要在 HTML 页面中嵌入图像，请使用< img >元素。图像被链接到网页上，而不是放入其中。< img >元素为指定的图像生成一个占位符。< figcaption >元素用于给图片添加标题。它是一个可选标签，可以在标签内容之前或之后。尽管元素本身可能包括几个附加组件，如或，但一个标签中只能嵌套一个元素。元素与元素一起使用，它可能是元素的第一个或最后一个子元素。一个<图>通常是一个图片、插图、图表、代码片段或在文档的主要流程中引用的另一个项目，但是可以在不中断主要流程的情况下重新定位到文本或附录的另一部分。<图>元素的内容轮廓从页面的主轮廓中省略，因为它是一个剖切根。通过将<图形标题>作为第一个或最后一个子元素放入其中，标题可以与<图形>元素连接。图的标题作为图中第一个<图标题>元素给出。

**语法:**

```html
<figure>
    <img src="....">
    <figcaption>.......</figcaption>
</figure>
```

**参数:**

1.  **img src:** 该标签在文档中用于包含图像源。
2.  **figcaption:** 该元素用于指定图像的标题。

**示例 1:** 在本示例中，为了在文档中标记极客头像，我们将使用<图形>元素和<图形标题>元素来指定图像的标题。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <title>geeksforgeeks</title>
  </head>
  <body>
    <figure>
      <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210823163000/1.png" 
           alt="gfg" width="320" height="250">
       <figcaption>
         GeeksforGeeks | A computer science portal for geeks
       </figcaption>
    </figure>
 </body>
</html>
```

**输出:**

![](img/cf9623dae1e91da6a8643862f9ca6b76.png)

**示例 2:** 在本例中，我们将使用一个带有**多个图像**的图形标签，嵌套在一个带有**单个标题**的单个<图形>元素中。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Page Title</title>
   </head>
   <body>
      <figure>
         <img src=
 "https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210727192049/CP_ad_icon.png" 
              width="110">
         <img src=
 "https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210203145720/DSA-SP_1-min.png" 
              width="110">
         <img src=
 "https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210609101834/GC-LIve-Icon-1.png"
             width="110">
         <figcaption>
           GeeksforGeeks | A computer science portal for geeks
         </figcaption>
      </figure>
   </body>
</html>
```

**输出:**

![](img/dd35a49c91cdaa2968213129ad43f3ca.png)