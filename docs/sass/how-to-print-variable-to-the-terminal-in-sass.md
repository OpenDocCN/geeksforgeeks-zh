# 如何在 SASS 中将变量打印到终端？

> 原文:[https://www . geeksforgeeks . org/如何将变量打印到终端-in-sass/](https://www.geeksforgeeks.org/how-to-print-variable-to-the-terminal-in-sass/)

SASS 有三种在用户终端或控制台上提供输出的方法。

**注意:**输出可能因实现而异，因编译器而异。

*   **Using @error rule:** When writing mixins and functions that take arguments, you usually want to ensure that those arguments have the types and formats your API expects. If they aren’t, the user needs to be notified and your mixin/function needs to stop running.

    萨斯让**@错误**规则变得简单，该规则写为**@错误**。它打印表达式的值(通常是字符串)以及指示当前 mixin 或函数是如何被调用的堆栈跟踪。一旦打印出错误，Sass 就停止编译样式表，并告诉运行它的任何系统发生了错误。

    **示例:**

    ```html
    @mixin reflexive-position($property, $value) {
      @if $property != top and $property != bottom {
        @error "Property #{$property} must be either top or bottom.";
      }

      $top-value: if($property == bottom, initial, $value);
      $bottom-value: if($property == bottom, $value, initial);

      top: $top-value;
      bottom: $bottom-value;
      [dir=rtl] & {
        top: $bottom-value;
        bottom: $top-value;
      }
    }

    .sidebar {
      @include reflexive-position(left, 12px);
    }
    ```

    这是编译器在 Dart CSS 中的样子:

    ```html
    Error: "Property left must be either top or bottom."
      ?
    3 ?     @error "Property #{$property} must be either top or bottom.";
      ?     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
      ?
      example.scss 3:5   reflexive-position()
      example.scss 19:3  root stylesheet

    ```

*   **Using @warn rule:** When writing mixins and functions, you may need to avoid users from passing some arguments or values. They may be passing legacy arguments that are now deprecated, or they may be calling your API in a way that is not quite optimal.
    The **@warn** rule is designed just for this. It’s written **@warn** and it prints the value of the expression (usually a string) for the user, along with a stack trace indicating how the current mixin or function was called. Unlike the **@error** rule, though, it doesn’t stop Sass entirely.

    **示例:** SASS 文件

    ```html
    $known-properties: webkit, hd;

    @mixin property($character, $value, $properties) {
      @each $property in $properties {
        @if not index($known-properties, $properties) {
          @warn "Unknown property #{$property}.";
        }

        -#{$property}-#{$character}: $value;
      }
      #{$character}: $value;
    }

    .tilt {
      @include property(transform, rotate(30deg), webkit hd);
    }
    ```

    **输出:** CSS 文件

    ```html
    .tilt {
      -webkit-transform: rotate(30deg);
      -hd-transform: rotate(30deg);
      transform: rotate(30deg);
    }

    ```

    这是编译器在 Dart CSS 中的样子:

    ```html
    Warning: Unknown property webkit.
        example.scss 6:7   property()
        example.scss 16:3  root stylesheet

    ```

*   **Using @debug rule:** Sometimes its useful to see the value of a variable or expression while you’re developing your stylesheet. That’s what the **@debug** rule is for: it’s written **@debug**, and it prints the value of expression, along with the filename and line number.

    **示例:** SASS

    ```html
    @mixin inset-divider-offset($offset, $padding) {
      $divider-offset: (2 * $padding) + $offset;
      @debug "divider offset: #{$divider-offset}";

      margin-left: $divider-offset;
      width: calc(100% - #{$divider-offset});
    }
    ```

    这是编译器在 Dart CSS 中的样子:

    ```html
    test.scss:3 Debug: divider offset: 132px

    ```

**注意:**可以将任意值传递给@debug，不只是字符串！它打印与 meta.inspect()函数相同的值的表示形式。