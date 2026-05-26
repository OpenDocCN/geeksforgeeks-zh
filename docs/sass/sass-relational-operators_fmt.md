# SASS | 关系运算符

> 原文: [https://www.geeksforgeeks.org/sass-relational-operators/](https://www.geeksforgeeks.org/sass-relational-operators/)

关系运算符是比较两个数的值的运算符。它们判断一个数字是小于还是大于或等于另一个数字。它们会自动将数字转换成兼容的单位。

*   `<expression> < <expression>` 返回第一个表达式的值是否小于第二个表达式的值。
*   `<expression> <= <expression>` 返回第一个表达式的值是否小于或等于第二个表达式的值。
*   `<expression> > <expression>` 返回第一个表达式的值是否大于第二个表达式的值。
*   `<expression> >= <expression>` 返回第一个表达式的值是否大于或等于第二个表达式的值。

**示例:**

```
@debug 100 > 50
```

**输出:**

```
true
```

```
@debug 10px > 17px
```

**输出:**

```
false
```

```
@debug 96px >= 1in
```

**输出:**

```
true
```

```
@debug 1001ms <= 1s
```

**输出:**

```
false
```

没有单位的数字可以和任何数字比较。这些无单位的数字会自动转换成其他数字的单位。

**示例:**

```
@debug 100 > 50px
```

**输出:**

```
true
```

```
@debug 10px > 17
```

**输出:**

```
false
```

只有单位不兼容的数字不能相互比较。

**示例:**

```
@debug 100px > 10s
```

**输出:**

```
*Error: Incompatible units px and s.*
```