# SASS |布尔和布尔运算符

> 原文:[https://www . geesforgeks . org/sass-booleans-and-boolean-operators/](https://www.geeksforgeeks.org/sass-booleans-and-boolean-operators/)

SASS 支持布尔值:

*   真实的
*   错误的

它用在条件编译中，其中表达式的计算结果是这些值中的任何一个。

**为变量指定一个布尔值:**

```html
$variable: true; or $variable: false;
```

**条件编译中的用法:**我们可以在条件编译中使用布尔值。请看下面的例子，我们在 mixin 中传递了一个真值，这样@if 块将被编译。

**SASS 文件:**

```html
@mixin button-format( $round-button, $size ) {
    color: white;
    background-color: blue;
    width: $size;

    @if $round-button {
        height: $size;
        border-radius: $size / 2; 
    }
}

.mybutton {
    @include button-format(true, 100px);
}

```

**编译后的 CSS 文件:**

```html
.mybutton {
    color: white;
    background-color: blue;
    width: 100px;
    height: 100px;
    border-radius: 50px;
}

```

**布尔运算符:**
SASS 有三个布尔运算符两个是二元:`and`、`or`一个是一元:`not`。

**二元运算符:**

1.  **and:**

    **语法:**

    ```html
    expression1 and expression2
    ```

    只有当两个表达式的计算结果都为真时，最终的布尔值才为真，否则为假。

2.  **or:**

    **语法:**

    ```html
    expression1 or expression2
    ```

    只有当任何表达式的计算结果为真时，最终的布尔值才为真，否则为假。

**一元运算符:**

*   **not:**

    **语法:**

    ```html
    not expression
    ```

    最终的布尔值将与表达式值相反。

请参见下面的示例:

```html
$var1: true and true;
$var2: true and false;

$var3: true or false;
$var4: false or false;

$var5: not true;

// @debug will print the values of the variable 
// at the compilation time in the terminal.
//------------  values

@debug $var1;  // true
@debug $var2;  // false

@debug $var3;  // true 
@debug $var4;  // false

@debug $var5;  // false

```