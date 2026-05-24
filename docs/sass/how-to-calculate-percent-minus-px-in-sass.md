# 如何计算 SASS 中的百分比减 px？

> 原文:[https://www . geesforgeks . org/如何计算百分比减-px-in-sass/](https://www.geeksforgeeks.org/how-to-calculate-percent-minus-px-in-sass/)

计算百分比和 px 之间的差异并不像 50%–30px 那么简单。显然你会得到不兼容的单位错误。这是因为 SASS 无法对无法从一个单位转换为另一个单位的值执行算术运算。SASS 不知道“百分比(%)”在像素或任何其他单位方面到底有多宽。只有浏览器能够知道这样的事情。

那么 **calc()** 功能的需求来了。

**关于 calc():**calc()函数允许我们对属性值执行数学运算。例如，我们可以使用 calc()指定宽度是两个或多个数值相加的结果，而不是声明元素宽度的静态像素值。

*   **Example:**

    ```html
    .class{
        height: calc(30px + 50px);
    } 
    ```

    **编译文件:**

    ```html
    .class {
      height: calc(30px + 50px);
    }
    ```

    **但是我们为什么需要这个呢？**
    **calc()函数**提供了更好的解决方案，原因如下。我们可以组合不同的单位。具体来说，我们可以将相对单位(如百分比和视口单位)与绝对单位(如像素)混合使用。例如，我们可以创建一个表达式，从百分比值中减去一个像素值。

*   **Example:**

    ```html
    .class {
        width: calc(50% + 30px);
    }
    ```

    **编译文件:**

    ```html
    .class {
      width: calc(50% + 30px);
    }
    ```

    现在让我们回到我们的例子，从%中减去 px。使用 SCSS 代码中的 **calc()** 函数，我们可以很容易地做两个不同单位的减法。

*   **Example:**

    ```html
    .class {
        height: calc(50% - 20px);
    }
    ```

    **编译文件:**

    ```html
    .class {
      height: calc(50% - 20px);
    }
    ```

    有时，如果您的值在变量中，您可能需要使用插值将它们转换为字符串。

*   **Example:**

    ```html
    $x: 50%;
    $y: 20px;

    .class {
      width: calc(#{$x} - #{$y});
    }
    ```

    **编译文件:**

    ```html
    .class {
      height: calc(50% - 20px);
    }
    ```

**注意:****calc()函数**可以用数值属性值进行加减乘除运算。具体来说，它可以用于长度、频率、角度、时间、数字或整数数据类型。

**例:**

```html
.class {
    width: calc(50vmax + 3rem);
    padding: calc(1vw + 1em);
    transform: rotate( calc(1turn + 28deg));
    background: hsl(100, calc(3 * 20%), 40%);
    font-size: calc(50vw / 3);
}
```

**编译文件:**

```html
.class {
  width: calc(50vmax + 3rem);
  padding: calc(1vw + 1em);
  transform: rotate(calc(1turn + 28deg));
  background: hsl(100, calc(3 * 20%), 40%);
  font-size: calc(50vw / 3);
}
```