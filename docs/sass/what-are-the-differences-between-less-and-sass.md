# 【LESS 和 SASS 有什么区别？

> 原文:[https://www . geesforgeks . org/less 和 sass 的区别是什么/](https://www.geeksforgeeks.org/what-are-the-differences-between-less-and-sass/)

本文旨在强调两个 CSS 预处理器 LESS 和 SASS 之间的关键特性和区别。在直接进入差异部分之前，首先，让我们谈谈这两个预处理器。如果你不知道这个预处理器的基础知识，那么请参考 [LESS](https://www.geeksforgeeks.org/introduction-to-less/) & [SASS](https://www.geeksforgeeks.org/css-preprocessor-sass/) 。

**LESS:** 这是一个**更精简的样式表**，本质上是动态的，并且高效地支持定制和可重用性。LESS 支持跨浏览器友好。它是基于 JavaScript 的，并且有非常精确的错误报告以及错误的准确位置指示。它通过让用户创建像变量和混合这样的属性来在整个项目中创建动态的和可重用的值，从而有助于可读性和可重用性。它使用 Preboot.less 来实现混合。

**示例:**

## 较少的

```html
@selector: box; //using variables

.@{selector} {
  font-weight: semi-bold;
  line-weight: 20px;
}
```

**CSS 输出:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
.box {
 font-weight: semi-bold;
 line-weight: 20px;
}
```

**SASS:** 这是一个**语法上令人敬畏的风格** **表单**，支持 CSS 的所有版本兼容扩展，增加了代码的可重用性。它使用 Ruby 实现，并主动报告语法中的错误。它使用 compass extension 来实现 mixins，并使用户能够实现自己的功能。它允许用户创建像变量和混合这样的代码可重用性。

**示例:**

## 厚颜无耻

```html
a {
  color: white;

  // Nesting
  &:hover {
    text-decoration: none;
  }

  :not(&) {
    text-decoration: underline;
  }
}
```

**CSS 输出:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
a {
  color: white;
}
a:hover {
  text-decoration: none;
}
:not(a) {
  text-decoration: underline;
}
```

**相似点**

1.  它们在语法上是相似的。

    *   **LESS:**

        ```html
         @color: white; /*@color is a LESS variable*/
        #header {
          color: @color;
        }
        ```

    *   **SASS:**

        ```html
         $color: white; /* $color is a SASS variable */
        #header {
          color: $color;
        }
        ```

2.  我们可以在 SASS 和 LESS 中使用像 mixins 和变量这样的属性。

**SASS&LESS 的区别:**

<figure class="table">

| 

SASS

 | 

LESS

 |
| --- | --- |
| It is based on Ruby and needs to be installed to run on windows. | Originally based on ruby, but now ported to JavaScript. Only the applicable javascript files need to be installed to run. |
| Report syntax errors. | More accurate error report with error location indication. |
| Use Compass extension to realize mashup. | Implement mixins with no pre-boot extension. |
| Enable users to create their own functions. | Manipulate values using JavaScript. |
| Use "{content }”x201；; For variables, "@" for mixins. | Use the variable "@". |

</figure>

**示例:**用于混合蛋白

**LESS:**

## 较少的

```html
.margined {
  margin-bottom: 1rem;
  margin-top: 2rem;
}
#box h1 {
  font: Roboto, sans-serif;
  .margined;
}
.cont a {
  color: blue;
  .margined;
}
```

**CSS 输出:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
#box h1 {
  font: Roboto, sans-serif;
  margin-bottom: 1rem;
  margin-top: 2rem;
}
.cont a {
  color: blue;
  margin-bottom: 1rem;
  margin-top: 2rem;
}
```

**SASS:**

## 厚颜无耻

```html
@mixin margined {
  margin-bottom: 1rem;
  margin-top: 2rem;
}
#box h1 {
  @include margined;
  font: Roboto, sans-serif;
}
.cont a {
  @include margined;
  color: blue;
}
```

**CSS 输出:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
#box h1 {
  margin-bottom: 1rem;
  margin-top: 2rem;
  font: Roboto, sans-serif;
}
.cont a {
  margin-bottom: 1rem;
  margin-top: 2rem;
  color: blue;
}
```