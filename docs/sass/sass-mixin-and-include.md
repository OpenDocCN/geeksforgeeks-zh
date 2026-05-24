# SASS | @mixin 和@include

> 原文:[https://www.geeksforgeeks.org/sass-mixin-and-include/](https://www.geeksforgeeks.org/sass-mixin-and-include/)

Mixins 可以用于对可以分配不同值的样式进行分组，并且可以像 function 一样多次使用。我们还可以在 mixin like 函数中传递参数，这允许我们编写可重用的代码。

mixin 是使用@mixin at-rule 定义的，可以在当前上下文中使用@include at-rule。

Mixins 有两种使用方式:**无参数和有参数。**

1.  **无参数:**这种类型的 mixin 是可以使用的，当我们不需要改变属性的值即我们想一次又一次地使用一组具有相同属性值的属性时。

    **语法:**

    *   定义 mixin:@ mixin name _ of _ mixin {…}
    *   在当前块中使用 mixin:@ include _ of _ mixin；。

    ```html
    @mixin block-name{
        property-1: value;
        property-2: value;
            ...
        property-n: value;
    }

    block-name2{
        @include block-name;
    }

    ```

    ### **SCSS 文件:**

    ```html
    @mixin first-mixin {
        width: 100%;
        overflow: hidden;
        color: gray;
    }

    @mixin second-mixin {
        @include first-mixin;

        ul {
            list-style-type: none;
        }

        li {
            display: inline-block;
            width: 100px;
            padding: 5px 10px;
        }

        li a {
            text-decoration: none;
        }

    }

    navigationbar {
        @include second-mixin;
    }

    ```

    ### **编译后的 CSS 文件:**

    ```html
    navigationbar {
        width: 100%;
        overflow: hidden;
        color: gray;
    }

    navigationbar ul {
        list-style-type: none;
    }

    navigationbar li {
        display: inline-block;
        width: 100px;
        padding: 5px 10px;
    }

    navigationbar li a {
        text-decoration: none;
    }

    ```

2.  **带有参数:**这种类型的 mixin 可以使用，当我们想要一次又一次地使用一组具有不同值的属性时，我们可以像函数一样使用参数传递不同的值。这里，参数默认值的概念与任何其他编程语言相同。

    **语法:**

    *   定义 mixin:@ mixin _ name of _ mixin(参数…) {…}
    *   Use mixin: @ includname _ of _ mixin (parameter …) in the current block;

    ```html
    // Here default values are optional

    @mixin block-name($parameter1, $parameter2: default, ...) {

        property-1: $parameter1;
        property-2: $parameter2;
        // You can use all the parameters 
        // same as variables
    }

    block-name2 {
        @include block-name($argument1, $argument2, ...);
    }

    ```

    ### **SASS 文件:**

    ```html
     // Here blue is default value of $three

    @mixin first-mixin($one, $two, $three: blue) {
        width: $one;
        overflow: $two;
        color: $three;
    }

    @mixin second-mixin($one, $two, $three, $four) {
        // Don't need to pass the third argument if 
            // the default value is same as your argument.
        @include first-mixin($one, $two /*, Default*/);

        ul {
            list-style-type: none;
        }

        li {
            display: inline-block;
            width: $four;
            padding: 5px 10px;
        }

        li a {
            text-decoration: none;
        }

    }

    navigationbar {
        @include second-mixin(100%, hidden, blue, 100px);
    }

    ```

    ### **编译后的 CSS 文件:**

    ```html
    navigationbar {
      width: 100%;
      overflow: hidden;
      color: blue;
    }

    navigationbar ul {
      list-style-type: none;
    }

    navigationbar li {
      display: inline-block;
      width: 100px;
      padding: 5px 10px;
    }

    navigationbar li a {
      text-decoration: none;
    }

    ```