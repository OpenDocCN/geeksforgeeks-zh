# SCSS 和 SASS 有什么区别？

> 原文:[https://www . geeksforgeeks . org/SCS 和 sass 的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-scss-and-sass/)

SASS(语法上令人敬畏的样式表)是一种预处理器脚本语言，将被编译或解释成 CSS。SassScript 本身是一种脚本语言，而 SCSS 是 SASS 的主要语法，它建立在现有 CSS 语法的基础上。它像 CSS(级联样式表)一样使用分号和括号。
SASS 和 SCSS 可以互相导入。Sass 实际上通过数学和变量支持使 CSS 更加强大。
我们来列举一下 SASS 和 SCSS 的主要区别。

*   当我们需要一个原始的语法时，使用 SASS，SCSS 不需要代码语法。
*   SASS 遵循严格缩进，SCSS 没有严格缩进。
*   SASS 有一个松散的语法，没有空格和分号，SCSS 更像 CSS 样式，分号和大括号的使用是强制性的。
*   SASS 文件扩展名为。sass 和 SCSS 文件扩展名为. scss。
*   SASS 拥有比 SCSS 更多的开发者社区和支持。

**SCSS 示例:**

## SCSS

```html
/* .scss file */
$bgcolor: blue;
$textcolor: red;
$fontsize: 25px;

/* Use the variables */
body {
  background-color: $bgcolor;
  color: $textcolor;
  font-size: $fontsize;
}
```

**输出 CSS:**

```html
body {
  background-color: blue;
  color: red;
  font-size: 25px;
}
/* now this can apply resulting html file */
```

**SASS 示例:**

## 厚颜无耻

```html
/* SASS */

$primary-color: green
$primary-bg: red

body 
  color: $primary-color
  background: $primary-bg
```

**输出 CSS:**

```html
/* CSS */
body {
  color: green;
  background: red;
}
```

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。