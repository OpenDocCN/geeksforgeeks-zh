# SASS @for Rule

> 原文:[https://www.geeksforgeeks.org/sass-for-rule/](https://www.geeksforgeeks.org/sass-for-rule/)

SASS 中规则的**@用于从一个数字到另一个数字的递增或递减计数，并检查在给定范围内的每个数字的部分。每个数字都分配了一个变量名称，可以在循环中访问。它**T3 可以有两种使用方式:****

**1。开始到结束:**在此类型中，“开始到结束”包括结束编号作为计数的一部分。

**语法:**

```html
@for <variable> from <expression> through <expression> {

    /* Body of loop that will be executed 
    when the condition is true */
}
```

**示例:**在本例中，我们将使用 through 语法。#{$i}部分是将变量(I)与文本组合成字符串的语法。

```html
@for $i from 1 through 3 {
    .col-#{$i} { width: 100%/3 * $i; }
}
```

**输出:**

```html
.col-1 {
  width: 33.3333333333%;
}

.col-2 {
  width: 66.6666666667%;
}

.col-3 {
  width: 100%;
}
```

**2。开始到结束:**在此类型中，“开始到结束”将结束编号排除在计数之外。

**语法:**

```html
@for <variable> from <expression> to <expression> {

    /* Body of loop that will be executed 
       when the condition is true */
}
```

**例:**

```html
@for $i from 1 to 5 {
  .column-#{$i} { width: 100%/4 * $i; }
}
```

**输出:**

```html
.column-1 {
  width: 25%;
}

.column-2 {
  width: 50%;
}

.column-3 {
  width: 75%;
}

.column-4 {
  width: 100%;
}
```