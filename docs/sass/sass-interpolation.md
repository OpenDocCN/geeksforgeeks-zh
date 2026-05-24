# SASS |插值

> 原文:[https://www.geeksforgeeks.org/sass-interpolation/](https://www.geeksforgeeks.org/sass-interpolation/)

插值基本上就是插入。插值允许我们将 sass 表达式插值到一个简单的 SASS 或 CSS 代码中。也就是说，您可以将选择器名称、属性名称、CSS at-rules、带引号或不带引号的字符串等定义为变量。插值是一种新的原理，它被广泛地应用于 SASS 中。

为了插入一个表达式，我们需要使用#{ }。

**语法:**

```html
......#{$variable_name}........
```

哪里…..代表一些文字。

请看下面的例子来获得更多的理解:
**SASS 文件:**

```html
@mixin interpolation($changeable, $val, $val2, $prop1, $prop2)
{
    background-#{$changeable}: $val;
    position: $val2;
    #{$prop1}: 0px; 
    #{$prop2}: 0px;
}

.blockarea{
    @include interpolation("image", url("img.png"), absolute, top, right);
}

.anotherbloakarea{
    @include interpolation("color", lightgray, absolute, top, left);
}

```

**编译后的 CSS 文件:**

```html
.blockarea {
    background-image: url("img.png");
    position: absolute;
    top: 0px;
    right: 0px;
}

.anotherbloakarea {
   background-color: lightgray;
   position: absolute;
   top: 0px;
   left: 0px;
}

```

**SASS 表达式中的插值总是返回未加引号的字符串，无论该字符串是否加引号。**

**插值的用途:**

1.  将动态创建的名称用作属性名、变量名或用于任何其他相同目的。
2.  创建一个可重用的代码；您可以将属性名、字符串、选择器名等定义为变量。