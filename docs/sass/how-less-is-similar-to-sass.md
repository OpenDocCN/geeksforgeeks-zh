# 【Less 和 Sass 有多像？

> 原文:[https://www.geeksforgeeks.org/how-less-is-similar-to-sass/](https://www.geeksforgeeks.org/how-less-is-similar-to-sass/)

**CSS 预处理程序**是一种编程语言，它扩展了 CSS 的所有特性，但它有助于使用不同的特性(如 mixins、变量和许多其他特性)来降低 CSS 的代码复杂性，这些特性使代码干净且易于理解。这些语言要求编译器将代码编译回正常的 CSS。

目前使用最多的两个 CSS 预处理程序是 **SASS 和 LESS。**虽然两者有很大的不同，但它们有一些相似的概念。在本文中，我们将讨论 LESS 和 SASS 之间的相似之处。

SASS 和 LESS 相似的方面如下:

1.  They are all CSS preprocessors.
2.  Concept of variable
3.  Mixed concept
4.  Nested concept
5.  Import concepts

现在，让我们逐一详细讨论这几点。

**1。CSS 预处理程序:**如前所述，SASS 和 LESS 都是 CSS 预处理程序，所以它们都需要一些特殊的编译器来将它们编译成常规的 CSS 文件，这些文件可以直接链接到 HTML 文件。

**2。变量:**变量是一个非常有用的元素，在很多流行的语言中都可以找到，比如 Python、Java 等等。这个特性在常规 CSS 中是不可用的，但是在 LESS 和 SASS 中，我们都可以分配变量来存储任何要多次使用的 CSS 值。这里唯一的区别是语法不同。

下面给出了两种语言中定义变量的语法:

**语法:**在 LESS 中定义变量

```html
@color_variable: red;
```

**语法:**在 SASS 中定义变量

```html
$color_variable: red;
```

**3。mixin:**mixin 就像一个包含一堆 CSS 属性的函数，可以在代码的任何地方使用。它们有参数，我们可以在调用不同元素时传递不同的值。LESS 和 SASS 都支持 Mixins 的特性。

下面给出了两种语言中定义混合的语法:

**语法:**在 LESS 中定义一个变量并在另一个类中使用它

```html
.button_mixin {
    color: blue;
    border: 2px solid black;
    padding: 1em;
}

.container {
    height: 100px;
    .button_mixin;
}
```

**语法:**在 SASS 中定义一个变量，并在另一个类中使用它

```html
@mixin button_mixin
    color: blue
    border: 2px solid black
    padding: 1em

container
    @include button_mixin
    height: 100px
```

**4。嵌套:**嵌套是编程语言中非常重要的概念。在嵌套中，我们可以在另一个代码块中编写一个代码块。SASS 和 LESS 都支持嵌套，但是它们的语法不同。

下面给出的语法显示了 LESS 和 SASS 中的嵌套特性:

**语法:**在 LESS 中定义变量

```html
nav {
    ul {
        margin: 0;
        padding: 0;
    }
    li {
        display: inline-block;
    }
    a {
        display: block;
        text-decoration: none;
    }
}
```

**语法:**在 SASS 中定义变量

```html
nav
  ul
    margin: 0
    padding: 0

  li
    display: inline-block

  a
    display: block
    text-decoration: none
```

**5。导入:**在 CSS 预处理程序中导入是一个特性，在这个特性中，我们可以将一个完整的 SASS 或 LESS 文件导入到另一个完整的文件中，包括所有的混合、变量和其他代码。这个特性为代码提供了一种模块化的方法，同时设计了一个大型网站，在这个网站上，在单个文件上编写代码可以使代码长度变得非常长，以便于阅读和导航来进行任何更正和更改。

使用导入功能，我们可以在不同的文件中编写代码的不同部分，最后将它们导入到一个主 SASS 或 LESS 文件中。SASS 和 LESS 都提供了这种导入功能，我们可以使用它们来使我们的代码更加干净。

下面给出了这两种语言的导入语法:

**语法:**在 LESS 中定义变量

```html
@import "sample1.less"
@import "sample2.less"
```

**语法:**在 SASS 中定义变量

```html
@import "sample"
@import "sample2"
```

因此，从以上几点，我们得到了 LESS 和 SASS 之间相似性的详细概述。它们在彼此之上还有一些额外的特征。最近，两者都被开发人员大量使用，并且都有各自的优缺点。选择基本上取决于开发人员自己的选择，而不是需要，因为他们两个几乎做同样的工作，但方式略有不同。