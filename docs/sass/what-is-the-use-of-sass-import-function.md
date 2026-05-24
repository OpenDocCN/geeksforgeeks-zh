# SASS @ import 功能有什么用？

> 原文:[https://www . geesforgeks . org/什么是使用 sass-import-function/](https://www.geeksforgeeks.org/what-is-the-use-of-sass-import-function/)

使用本机 CSS 语言编写代码有时会非常混乱、冗长和复杂。为了降低编写 CSS 代码的复杂性，我们使用了 CSS 预处理程序。最常用的 CSS 预处理程序之一是 SASS。在本文中，我们将学习在 SASS 中使用@import 函数。

**SASS @import** 功能帮助我们一起导入多个 SASS 或者 CSS 样式表，这样就可以一起使用了。使用@import 规则导入一个 SASS 文件，允许对导入另一个文件的另一个文件的 mixins、变量和函数进行访问。

**语法:**

```html
@import path_of_file
```

我们可以只使用逗号将多个 SASS 文件导入到一个 SASS 文件中。在我们必须导入大量文件的情况下，这使得代码变得更加容易。

**语法:**

```html
@import file1, file2, file3
```

**示例:**下面给出的是一个代码示例，我们创建了两个名称分别为 *style1.sass* 和 *style2.sass* 的单独的 sass 文件，并将 sass 代码添加到其中，然后，我们将这两个 SASS 文件导入到最终的 *style.sass* 文件中。

**文件名:style1.sass**

```html
.btn1
    background-color: blue
    font-size: 2em
    color: white
```

**文件名:style2.sass**

```html
.btn2
    color: blue
    background-color: aqua
    font-size: 2em
```

**文件名:style.sass**

```html
@import style4, style3
```

**输出:**如果编译了以上代码，那么最终的 CSS 文件即“style.css”文件将如下:

## CSS

```html
.btn1 {
  background-color: blue;
  font-size: 2em;
  color: white;
}

.btn2 {
  color: blue;
  background-color: aqua;
  font-size: 2em;
}
```

**注意:**虽然@import 函数是一个非常有用的 SASS 特性。但是，它有一些主要的缺点，如下所示:

*   @import makes all variables, mixins and other features globally available, which makes the library difficult to maintain because it often leads to some naming conflicts.
*   It also has some security risks, because it allows every user to edit and change everything on a global scale.
*   The @extend rule in SASS is also global, which makes it difficult for programmers to determine which style to extend.

由于所有这些困难<u>，</u>SASS 团队不鼓励使用@import 函数，并且在未来几年内可能会将其从语言中移除。我们在 SASS 库中有另一个@use 函数来解决上述问题，而不是@import 函数。