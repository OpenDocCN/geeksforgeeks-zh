# SASS | @if 和@else

> 原文:[https://www.geeksforgeeks.org/sass-if-and-else/](https://www.geeksforgeeks.org/sass-if-and-else/)

@if，@else，@else-if 允许我们像 JavaScript 一样控制 SASS 文件编译中的流。

1.  **@if**: @if block will be compiled if the value of the conditional expression is true.

    **语法:**

    ```html
    @if <conditional_expression> { ... }
    ```

    **示例 1:** SASS 文件

    ```html
    @mixin button-format( $round-button, $size ) {
        color: white;
        background-color: blue;
        width: $size;

        @if $round-button {
            height: $size;
            border-radius: $size / 2; 
        }
    }

    .mybutton{
        @include button-format(false, 100px);
    }

    ```

    **示例 1:** 编译后的 CSS 文件

    ```html
    .mybutton {
      color: white;
      background-color: blue;
      width: 100px;
    }

    ```

    **示例 2:** SASS 文件

    ```html
    @mixin button-format( $round-button, $size ) {
        color: white;
        background-color: blue;
        width: $size;

        @if $round-button {
            height: $size;
            border-radius: $size / 2; 
        }
    }

    .mybutton{
        @include button-format(true, 100px);
    }

    ```

    **示例 2:** 编译后的 CSS 文件

    ```html
    .mybutton {
        color: white;
        background-color: blue;
        width: 100px;
        height: 100px;
        border-radius: 50px;
    }

    ```

2.  **@else:** If the values of conditional expressions of all the above @if or @else-if blocks are false, then this block will be compiled.

    **语法:**

    ```html
    @else { ... }
    ```

    **SASS 文件:**

    ```html
    @mixin theme ($theme-decide, $r, $g, $b) {
        // light background
        @if $theme-decide {
            background-color: rgba($r, $g, $b, 0.5);
        }
        // dark background
        @else {
            background-color: rgba($r, $g, $b, 1); // red color
        }

    }

    .myblock {
        @include theme(false, 255, 0, 0);
    }

    ```

    **编译后的 CSS 文件:**

    ```html
    .myblock {
        background-color: red;
        // if true value is passed then rgba(255, 0, 0, 0.5);
    }

    ```

3.  **@else if:** The first @else-if block with conditional expression value true will be compiled. If no @else-if block expression evaluates to true then @else block will be compiled.

    **语法:**

    ```html
    @else if <conditional_expression> { ... }
    ```

    **SASS 文件:**

    ```html
    @mixin theme ($theme-decide, $r, $g, $b) {
        // light background
        @if $theme-decide == 1 {
            background-color: rgba($r, $g, $b, 0.5);
        }
        // medium-dark background
        @else if $theme-decide == 2 {
            background-color: rgba($r, $g, $b, 0.7);
        }
        // dark background
        @else {
            background-color: rgba($r, $g, $b, 1);
        }

    }

    .myblock {
        @include theme(2, 0, 255, 0);
    }

    ```

    **编译后的 CSS 文件:**

    ```html
    .myblock {
      background-color: rgba(0, 255, 0, 0.7);
    }

    ```