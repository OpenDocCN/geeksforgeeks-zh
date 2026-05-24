# SASS |负变量值

> 原文:[https://www.geeksforgeeks.org/sass-negative-variable-value/](https://www.geeksforgeeks.org/sass-negative-variable-value/)

SASS 变量在为网页编写可维护的样式代码时非常有用。通常，我们要求页面的不同组件具有相同的样式属性值。在这种情况下，为变量赋值并在任何需要的地方使用它可以减少将来更改样式所需的工作量。有时，我们可能还需要对一个属性值进行否定。例如，考虑下面给出的 SASS 代码:

```html
$marg: 20px;

#div1 {
    margin: 0 20px 0 -20px;
}
```

属性值`20px`和`-20px`可以用$marg 变量代替。最明显的方法是:

```html
$marg: 20px;

#div1 {
    margin: 0 $marg 0 -$marg;
}
```

但是，在编译时，这会生成以下 css:

```html
$marg: 20px;

#div1 {
    margin: 0 20px -20px;
}
```

这是因为 SASS 编译器把`0 -$marg`当作减法运算，输出-20px。因此，每当我们希望使用一个变量的否定时，它可能会导致不希望的输出 CSS，因为 SASS 编译器可能会将意图误认为是二进制减法。

现在有多种方法可以解决这个问题。

1.  **使用括号:**用括号括住变量会阻止编译器执行减法。

    ```html
    $marg: 20px;

    #div1 {
        margin: 0 $marg 0 (-$marg);
    }
    ```

2.  **与负数相乘:**简单地将变量与-1 相乘将产生其否定，同时保留其原始单位。

    ```html
    $marg: 20px;

    #div1 {
        margin: 0 $marg 0 -1*$marg;
    }
    ```

3.  **使用插值:**对值进行插值会将其转换为不带引号的字符串。它可以用来获得变量值的否定。但是，不建议这样做，因为输出 CSS 中的不带引号的字符串看起来像一个数字，但不能与数字运算符和函数一起使用，这可能会导致代码误导。

    ```html
    $marg: 20px;

    #div1 {
        margin: 0 $marg 0 -#{$marg};
    }
    ```

在上述所有方法中，编译时获得以下 CSS:

```html
#div1 {
    margin: 0 20px 0 -20px;
}

```

通过这种方式，我们可以将一个 SASS 变量用于正用例和负用例，从而促进变量重用和更易维护的代码。