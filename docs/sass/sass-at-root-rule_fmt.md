# Sass | @at-root 规则

> 原文: [https://www.geeksforgeeks.org/sass-at-root-rule/](https://www.geeksforgeeks.org/sass-at-root-rule/)

`@at-root` 规则在文件的根部发出其内部的所有内容，而不是使用普通的嵌套。它主要用于高级嵌套过程中，结合 SassScript [父选择器](https://www.geeksforgeeks.org/sass-parent-selector/)和[选择器函数](https://www.geeksforgeeks.org/sass-selector-functions/?ref=rp)。

## 语法

```html
@at-root <selector> { ... }
```

## 示例

```html
@use "sass:selector"

@mixin geeks($gfg)
  @at-root #{selector.unify(&, $gfg)}
    @content

.block .font
  @include geeks("input")
    times new roman

@include geeks("select")
    arial
```

这将导致以下输出:

```html
.block input.font {
  times new roman;
}

.block select.font {
  arial;
}
```

在上面的例子中需要 `@at-root` 规则，因为 Sass 不知道在执行选择器嵌套时用于生成选择器的插值。它会自动将外部选择器添加到内部选择器中，即使它被用作 Sass 表达式。Sass 被 `@at-root` 规则明确告知不要包含外部选择器。

## 样式规则

`@at-root` 规则可以摆脱样式规则。默认情况下，只包括像 `@media` 这样的 at 规则。但如果需要，可以控制结果中包含什么和不包含什么。

### 示例

```html
@media geeks
  .gfg
    color: green

@at-root (without: media)
      font-family: times new roman

@at-root (with: rule)
      font-size: 4px
```

这将导致以下输出:

```html
@media geeks {
  .gfg {
    color: green
  }
}
.gfg {
  font-family: times new roman
}
.gfg {
  font-size: 4px;
}
```

除了名称，查询中还可以使用一些其他特殊值:

*   `rule` 表示样式规则，这排除了所有 at 规则，但保留了样式规则。
*   `all` 表示必须排除所有 at 规则和样式规则。