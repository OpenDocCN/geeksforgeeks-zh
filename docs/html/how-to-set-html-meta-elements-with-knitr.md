# 如何用编织器设置 HTML 元元素？

> 原文:[https://www . geesforgeks . org/how-set-html-meta-elements-with-knitter/](https://www.geeksforgeeks.org/how-to-set-html-meta-elements-with-knitr/)

有时，您可能想要生成一些 R 代码，或者任何其他代码，而不将其包装在`标签中，或者您可能想要指定一些没有特定元素的元素。好吧，你现在需要的是使用 knitr 设置元元素。`

元数据是指关于数据的信息。HTML 中的<元>标签提供了关于 HTML 文档的信息，或者简单地说，它提供了关于文档的重要信息。这些标签基本上是用来添加名称/值对来描述 HTML 文档的属性，比如截止日期、作者姓名、关键词列表、文档作者等。一个 web 文档可以根据信息包含一个或多个元标签，但一般来说，它不会影响文档的物理外观。

**语法:**

```html
<meta name="meta-name-here"<!—the knitr method—>
```

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="author" content=
          "<!--rinline I(Sys.getenv('GeeksforGeeks')) -->">
    <meta name="date" content=
          "<!--rinline I(as.character(Sys.time())) -->">
</head>

<body></body>

</html>
```

**示例 2:**

## HTML

```html
<head>
    <!--begin.rcode results='asis', echo=TRUE
    cat('
      <meta name="author" content="', 
            Sys.getenv('GeeksforGeeks'), '"> 

      <meta name="date" content="', 
            as.character(Sys.time()),'-->">
    ',sep="")
    end.rcode-->
</head>
```

**注意:**两个示例都不包含正文部分或任何显示 HTML 元素，因此不会显示任何输出结果。