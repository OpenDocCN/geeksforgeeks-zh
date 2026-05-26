# 如何在 SASS 中将变量打印到终端？

> 原文: [https://www.geeksforgeeks.org/how-to-print-variable-to-the-terminal-in-sass/](https://www.geeksforgeeks.org/how-to-print-variable-to-the-terminal-in-sass/)

SASS 有三种在用户终端或控制台上提供输出的方法。

**注意:** 输出可能因实现而异，因编译器而异。

## 使用 @error 规则

当编写接受参数的 mixins 和函数时，你通常希望确保这些参数具有你的 API 所期望的类型和格式。如果不符合，就需要通知用户，并且你的 mixin/函数需要停止运行。

SASS 让 `@error` 规则变得简单，该规则写为 `@error`。它打印表达式的值（通常是字符串）以及指示当前 mixin 或函数是如何被调用的堆栈跟踪。一旦打印出错误，Sass 就停止编译样式表，并告诉运行它的任何系统发生了错误。

**示例:**

```scss
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

```
Error: "Property left must be either top or bottom."
  ?
3 ?     @error "Property #{$property} must be either top or bottom.";
  ?     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  ?
  example.scss 3:5   reflexive-position()
  example.scss 19:3  root stylesheet
```

## 使用 @warn 规则

当编写 mixins 和函数时，你可能需要避免用户传递某些参数或值。他们可能传递了现已弃用的旧参数，或者可能以不太理想的方式调用你的 API。
`@warn` 规则正是为此设计的。它写为 `@warn`，它向用户打印表达式的值（通常是一个字符串），以及指示当前 mixin 或函数如何被调用的堆栈跟踪。与 `@error` 规则不同，它不会完全停止 SASS。

**示例:** SASS 文件

```scss
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

```css
.tilt {
  -webkit-transform: rotate(30deg);
  -hd-transform: rotate(30deg);
  transform: rotate(30deg);
}
```

这是编译器在 Dart CSS 中的样子:

```
Warning: Unknown property webkit.
    example.scss 6:7   property()
    example.scss 16:3  root stylesheet
```

## 使用 @debug 规则

有时在开发样式表时，查看变量或表达式的值很有用。这就是 `@debug` 规则的用途：它写为 `@debug`，它打印表达式的值，以及文件名和行号。

**示例:** SASS

```scss
@mixin inset-divider-offset($offset, $padding) {
  $divider-offset: (2 * $padding) + $offset;
  @debug "divider offset: #{$divider-offset}";

  margin-left: $divider-offset;
  width: calc(100% - #{$divider-offset});
}
```

这是编译器在 Dart CSS 中的样子:

```
test.scss:3 Debug: divider offset: 132px
```

**注意:** 可以将任意值传递给 `@debug`，不只是字符串！它打印与 `meta.inspect()` 函数相同的值的表示形式。