# CSS At-规则

> 原文：`https://www.geeksforgeeks.org/css-at-rules/`

Sass 支持作为适当 CSS 一部分的每个 at 规则。为了保持灵活性并与即将到来的 CSS 版本兼容，Sass 提供了通用支持，几乎涵盖了所有 at-rules。

## 语法

```html
@<rule> <value>, @<rule> {
   ... 
}
```

或者

```html
@<rule> <value> {
   ... 
}
```

规则必须始终是一个`标识符`，值（如果存在）可以是任何东西。规则和值都可以有`插值`。如果任何一个 CSS at-rule 嵌套在一个样式规则中，那么这两个规则会交换它们自己的位置，这样 at-rule 就在 CSS 输出的顶层，而样式规则就在它里面。这使得添加条件样式变得容易，无需重写样式规则选择器。

## 示例

```html
.gfg {
  margin: 4px;

@media geeks { margin: 8px; }
}
```

## 输出

```html
.gfg {
  margin: 4px;
}
@media geeks {
  .gfg {
    margin: 8px;
  }
}
```

## `@media` 规则

除了允许插值，`@media` 规则允许在查询中直接使用`Sass Script`表达式。只要有可能，Sass 还会合并相互嵌套的媒体查询，以便于支持当前不支持嵌套的`@media`规则的浏览器。

### 示例

```html
@media (hover: hover) {
  .gfg:hover {
    border: 4px solid green;

@media (color) {
      border-color: black;
    }
  }
}
```

### 输出

```html
@media (hover: hover) {
  .gfg:hover {
    border: 4px solid green;
  }
}
@media (hover: hover) and (color)
{
  .gfg:hover {
    border-color: black;
  }
}
```

## `@supports` 规则

`@supports`规则也允许在声明查询中使用`Sass Script`表达式。

### 示例

```html
@mixin gfg {
  font-family: arial;
  @supports (font-family: geeks ) {
    font-family: geeks;
  }
}

.header {
  @include gfg;
}
```

### 输出

```html
.header {
  font-family: arial;
}
@supports (font-family: geeks) {
  .header {
    font-family: geeks;
  }
}
```

## `@keyframes` 规则

`@keyframes`规则的工作原理与任何其他常规 at 规则一样。唯一不同的是，它的子规则应该是一些有效的关键帧规则（`%`、`from`或`to`），而不是任何普通的选择器。

### 示例

```html
@keyframes font-change {
  from {
    font-family: arial;
    color: black;
  }

  50% {
    font-family: sans;
    color: green;
  }

  to {
    font-family: algerian;
    color: cyan;
  }
}
```

### 输出

```html
@keyframes font-change {
  from {
    font-family: arial;
    color: black;
  }
  50% {
    font-family: sans;
    color: green;
  }
  to {
    font-family: algerian;
    color: cyan;
  }
}
```