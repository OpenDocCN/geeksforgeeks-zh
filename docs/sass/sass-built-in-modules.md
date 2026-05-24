# SASS |内置模块

> 原文:[https://www.geeksforgeeks.org/sass-built-in-modules/](https://www.geeksforgeeks.org/sass-built-in-modules/)

就像任何其他编程语言一样，SASS 提供了许多内置模块，这些模块包含各种有用的功能和一些混合，使其易于使用。模块将使用 **@use 规则**加载，就像任何其他用户定义的样式表一样，类似地，它的函数可以像任何其他模块成员一样被调用。所有内置模块都以 **sass:** 开头，以表明它们不同于其他模块，是 sass 本身的一部分。
**兼容性:**目前只有 Dart Sass 支持使用内置模块。像 LibSass 或 Ruby Sass 这样的其他实现需要使用它们的全局名称来调用函数，而不是使用@use 规则。

**示例:**

```html
@use "sass:color"
.button
  color: green
  border: 2px solid color.scale(green, $lightness: 20%)
```

这将导致以下 CSS 输出:

```html
.button {
  color: green
  border: 2px solid #20b2aa;
}

```

SASS 提供以下内置模块:

*   数学模块给出了处理数字的函数。
*   **sass:string** 模块提供了帮助组合、拆分或搜索字符串的功能。
*   **sass:color** 模块在现有颜色的基础上提供新的颜色，帮助你制作主题。
*   **sass:list** 模块帮助访问和修改列表的值。
*   **sass:map** 模块使使用地图变得更加容易。
*   **sass:选择器**模块提供对 sass 选择器引擎的访问。
*   **sass:meta** 模块给出了 sass 内部工作的细节。

在引入 SASS 模块之前，所有的 SASS 功能在任何时候都是全球可用的。它们中的许多仍然具有全局访问权限，这意味着它们仍然可以在不使用模块的情况下被访问。它们的使用将逐渐被 SASS 团队否决，直到它们可以在旧的 SASS 版本和目前不支持模块的 LibSass 中访问。几乎所有的功能都被添加到模块中，但是有些功能仍然只能在全球范围内使用。原因要么是因为它们有一些特殊的求值行为，比如 if()函数，要么是因为它们在内置 CSS 函数的基础上增加了一些额外的行为，比如`rgb()`和`hsl()`函数。这些在未来也不会被弃用，因此可以自由使用。