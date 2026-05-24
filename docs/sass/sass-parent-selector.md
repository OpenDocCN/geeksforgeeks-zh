# SASS |父选择器

> 原文:[https://www.geeksforgeeks.org/sass-parent-selector/](https://www.geeksforgeeks.org/sass-parent-selector/)

父选择器是 SASS 中的一种特殊类型的选择器，它允许我们以有效的方式重用外部(父)选择器。请看下面的例子来了解这个想法:

**例如:**假设我们有以下 CSS 样式块，

```html
a {
    text-decoration: none;
    display: inline-block;
    background-color: lightgray;
}

```

现在，你想添加悬停效果到锚块，然后你会写

```html
a:hover {
    background-color: gray;
}

```

使用 SASS 你不需要重复外部选择器(a)，你也可以做以下操作:
**SASS 文件:**

```html
a {
    text-decoration: none;
    display: inline-block;
    background-color: lightgray;

    &:hover {
        background-color: gray;
    }
}

```

这里 **&被称为父选择器。**编译后的 CSS 文件将与我们的 CSS 样式相同。

**编译后的 CSS 文件:**

```html
a {
    text-decoration: none;
    display: inline-block;
    background-color: lightgray;
}

a:hover {
    background-color: gray;
}

```

**优势:**

1.  You can create new classes with prefix or suffix as the name of the parent selector, which enables us to write
    very structured CSS styling, very efficiently.

    **SCS 档案:**

    ```html
    .main-block {
        border: 1px solid black;
        position: relative;

        &_subblock1 {
            position: absolute;
            display: block;
        }

        &_subblock2 {
            position: absolute;
            display: inline-block;
        }

    }

    ```

    **编译后的 CSS 文件:**

    ```html
    .main-block {
      border: 1px solid black;
      position: relative;
    }

    .main-block_subblock1 {
      position: absolute;
      display: block;
    }

    .main-block_subblock2 {
      position: absolute;
      display: inline-block;
    }

    ```

2.  您可以使用不同的伪类或伪元素在外部(父)选择器中添加样式。参见
    中我们使用的第一个例子:悬停伪类，用父选择器在锚点标签中添加效果。