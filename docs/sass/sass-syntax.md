# SASS |语法

> 原文:[https://www.geeksforgeeks.org/sass-syntax/](https://www.geeksforgeeks.org/sass-syntax/)

[SASS](https://www.geeksforgeeks.org/css-preprocessor-sass/) 支持两种语法。每一个都可以不同地用来加载你需要的 CSS，甚至其他语法。

**1。SCSS:**SCSS 语法使用**。scss** 文件扩展名。和 CSS 很像。你甚至可以说 SCSS 是 CSS 的超集，这意味着所有有效的 CSS 也是有效的 SCSS。由于它与 CSS 的相似性，它是最简单和流行的 SASS 语法。

**示例:**

```html
@mixin hover($duration) {
  $name: inline-#{unique-id()};

  @keyframes #{$name} {
    @content;
  }

  animation-name: $name;
  animation-duration: $duration;
  animation-iteration-count: infinite;
}

.gfg {
  @include hover(2s) {
    from { background-color: green }
    to { background-color: black }
  }
}
```

这将导致以下 CSS:

```html
.gfg {
  animation-name: inline-uf1ia36;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}
@keyframes inline-uf1ia36 {
  from {
    background-color: green;
  }
  to {
    background-color: black;
  }
}

```

**2。缩进语法:**这个语法是 SASS 的原始语法，它使用**。sass** 因为它是一个文件扩展名，正因为如此，它有时被简称为 sass。这种语法具有与 SCSS 相同的所有特征，唯一的区别是 SASS 使用缩进而不是 SCSS 的花括号和分号。

**示例:**

```html
@mixin hover($duration)
  $name: inline-#{unique-id()}

  @keyframes #{$name}
    @content

  animation-name: $name
  animation-duration: $duration
  animation-iteration-count: infinite

.gfg
  @include hover(2s)
    from
      background-color: green
    to
      background-color: black
```

这将导致以下 CSS:

```html
.gfg {
  animation-name: inline-uf1ia36;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}
@keyframes inline-uf1ia36 {
  from {
    background-color: green;
  }
  to {
    background-color: black;
  }
}

```