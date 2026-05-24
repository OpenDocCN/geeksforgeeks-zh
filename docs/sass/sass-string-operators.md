# SASS |字符串运算符

> 原文:[https://www.geeksforgeeks.org/sass-string-operators/](https://www.geeksforgeeks.org/sass-string-operators/)

Sass 支持一些可用于生成字符串的运算符。

*   <expression>**+** <表达式>返回一个包含两个表达式值的字符串。如果任一值是带引号的字符串，则结果将带引号；否则，它将被取消引用。</expression>
*   <expression>**/** <表达式>返回一个包含两个表达式值的不带引号的字符串，用/分隔。</expression>
*   <expression>**–**<表达式>返回一个未加引号的字符串，该字符串包含两个表达式的值，用-分隔。这是一个遗留操作符，一般应该使用[插值](https://www.geeksforgeeks.org/sass-interpolation/)来代替。</expression>

**示例:**

```html
@debug "Geeks" + "forGeeks" 
```

**输出:**

```html
"GeeksforGeeks"
```

```html
@debug Geeks + forGeeks
```

**输出:**

```html
GeeksforGeeks
```

```html
@debug #{20px + 10px} / 50px
```

**输出:**

```html
30px/50px
```

```html
@debug Geeks - for - Geeks
```

**输出:**

```html
Geeks-for-Geeks
```

以上运算符不仅用于字符串，还用于任何可以在 CSS 中编码的值。但是，您必须了解以下例外情况:

*   数字不能用作等式的左数值，因为它们有自己的运算符。
*   颜色不能用作等式中的左边值，因为它们曾经有自己的运算符。

```html
@debug "Elapsed time: " + 40s
```

**输出:**

```html
"Elapsed time: 40s"
```

```html
@debug true + " is a boolean value"
```

**输出:**

```html
"true is a boolean value"
```

**注意:**始终尝试使用插值来创建字符串，因为它们更干净、更清晰，而不是使用运算符。

**一元运算符**
由于一些历史原因，Sass 还支持/和–作为只取一个值的一元运算符:

*   **/** <表达式>返回一个不带引号的字符串，以/开头，后跟表达式的值。
*   **–**<表达式>返回一个不带引号的字符串，以–开头，后跟表达式的值。

```html
@debug / geeks
```

**输出:**

```html
/geeks
```

```html
@debug - geeks
```

**输出:**

```html
-geeks
```