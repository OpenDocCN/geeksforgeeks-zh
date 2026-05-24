# 如何使用 CSS 创建类？

> 原文:[https://www . geesforgeks . org/如何使用-css 创建类/](https://www.geeksforgeeks.org/how-to-create-classes-using-css/)

CSS 中一个类是一组 CSS 属性，如字体样式、高度、宽度、颜色等。当在 HTML 标记中用作属性时，CSS 样式应用于该标记。

#### 语法:

```html
.class_name {
    CSS attributes;
}
```

一个**时期**字符或符号“**”。**“是用的，后面跟着类名。然后给出左括号和右括号“ **{ }** ”，其中声明了 CSS 样式。

**说明:<样式/ >** 标签用于定义**内的 CSS 样式。HTML** 文件。一**时期**人物**。”**用于声明一个类，该类后面跟有类名，在我们的例子中是**“绿色文本”**。然后我们给出左括号和右括号“ **{ }** ”，在其中定义 CSS 属性。

## 超文本标记语言

```html
<style>

.green-text {
  /* CSS properties*/
  color: green;
  font-size:250%;
}

</style>
```

**将我们的 CSS 类分配给一个 HTML 标签:**

**说明**:在下面的实现中，我们已经将**【绿文】** CSS 类分配给了 [< /p >](https://www.geeksforgeeks.org/html-paragraph/) 标签，这将把我们的 CSS 样式应用到那个 [< /p >](https://www.geeksforgeeks.org/html-paragraph/) 标签的内容中。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
/*CSS class*/
.green-text {
  color: green;
  font-size:250%;
}
</style>
</head>
<body>

  <!-- class "green-text" is assigned to the </p>
 tag -->
<p class="green-text">Welcome to GeeksforGeeks</p>

</body>
</html>
```

**输出:**

![](img/6369bcae8c2c1083201fe324532b898d.png)

如您所见，我们已经成功地使用 CSS 创建了一个类，并将其分配给了一个 HTML 元素。关于 **CSS** 的更多知识，选择器可以浏览[这篇](https://www.geeksforgeeks.org/css-syntax-and-selectors/)文章。