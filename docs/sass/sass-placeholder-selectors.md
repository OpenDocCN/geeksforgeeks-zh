# SASS |占位符选择器

> 原文:[https://www.geeksforgeeks.org/sass-placeholder-selectors/](https://www.geeksforgeeks.org/sass-placeholder-selectors/)

占位符是另一种特殊的选择器。当您编写自己的 SASS 库时，会用到它。它的工作非常类似于没有参数的 mixin。

占位符选择器以%符号开头。

**语法:**

```html
%( name_of_selector ) { property: value; ... }
```

占位符选择器在 SASS 文件的编译中被排除(这定义了它的主要功能。请参见下面的“占位符选择器的使用”)。所以问题是:**怎么用？**

要使用占位符选择器，我们使用**@扩展** at-rule。

**语法:**

```html
@extend %( name_of_selector );
```

**示例:**

**SASS 文件:**

```html
%button-format {
    padding: 10px 20px;
    border-radius: 15px;
    color: black;
}

.toolbar-button {
    @extend %button-format;
    background-color: lightpink;

    &:hover {
        background-color: rgb(155, 106, 114);
    }
}

.status-bar-button {
    @extend %button-format;
    background-color: lightblue;

    &:hover {
        background-color: blue;
    }
}

```

**编译后的 CSS 文件:**

```html
.status-bar-button, .toolbar-button {
    padding: 10px 20px;
    border-radius: 15px;
    color: black;
  }

  .toolbar-button {
    background-color: lightpink;
  }
  .toolbar-button:hover {
    background-color: #9b6a72;
  }

  .status-bar-button {
    background-color: lightblue;
  }
  .status-bar-button:hover {
    background-color: blue;
  }

```

**占位符选择器的使用:**
占位符选择器在 SASS 文件的编译中被排除，因此用于创建 SASS 库。我们可以使用它预定义一些模板，然后我们可以随时通过@extend at-rule 来使用它，如上例所示。