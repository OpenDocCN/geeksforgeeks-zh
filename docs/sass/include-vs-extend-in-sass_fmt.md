# @在 SASS 中包含 vs @扩展

> 原文:[https://www.geeksforgeeks.org/include-vs-extend-in-sass/](https://www.geeksforgeeks.org/include-vs-extend-in-sass/)

`@include` 关键字用于包含编写在 `mixin` 块中的代码。`@mixin` 用于对需要多次重用的 css 代码进行分组。而在 SASS 中使用 `@extend` 从另一个 css 选择器继承(共享)属性。`@extend` 在元素几乎相同或完全相同时最有用。
两者的主要区别在于各自编译的 CSS 文件。

## @include 示例

**SCSS file:**

```scss
@mixin text {
  color: black;
  font-size: 30px;
  font-weight: bold;
}
.hello{
  @include text; 
}
.world{
  @include text;
}
```

`Mixin` 在 CSS 中的所有类上复制样式。

**编译 CSS 文件:**

```css
.hello{
  color: black;
  font-size: 30px;
  font-weight: bold;
}
.world{
  color: black;
  font-size: 30px;
  font-weight: bold;
}
```

如果需要，`Mixin` 也可以接受参数，而使用 `extend` 则不可能。
欲了解`@mixin` 的更多详情，请访问[此处](https://www.geeksforgeeks.org/sass-mixin-and-include/)

## @extend 示例

在此示例中，两个按钮将共享按钮的通用属性，但它们仅在背景颜色上有所不同。因此，在元素几乎相同且仅某些属性不同的情况下，使用 `@extend` 是一个好主意。

**SCSS file:**

```scss
%button-format {
    padding: 10px 20px;
    border-radius: 15px;
    color: black;
}

.toolbar-button {
    @extend %button-format;
    background-color: lightpink;

    &:hover {
        background-color: rgb(155, 106, 114);
    }
}

.status-bar-button {
    @extend %button-format;
    background-color: lightblue;

    &:hover {
        background-color: blue;
    }
}
```

**编译好的 CSS 文件:**

```css
.status-bar-button, .toolbar-button {
  padding: 10px 20px;
  border-radius: 15px;
  color: black;
}

.toolbar-button {
  background-color: lightpink;
}
.toolbar-button:hover {
  background-color: #9b6a72;
}

.status-bar-button {
  background-color: lightblue;
}
.status-bar-button:hover {
  background-color: blue;
}
```

## 结论

SASS 是一种非常棒的样式表语言，它的`@include` 和`@extend` 这两个特性都有优点和缺点。尽管如此，如果在确切的情况下使用，它们可以被证明是 SASS 最好的工具。