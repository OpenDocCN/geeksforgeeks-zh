# PHP 中的 `|` 和 `||` (or) 运算符有什么区别？

> 原文: [https://www.geeksforgeeks.org/what-is-the-difference-between-the-and-or-operator-in-php/](https://www.geeksforgeeks.org/what-is-the-difference-between-the-and-or-operator-in-php/)

## `|` 操作符

它是按位或运算符。如果设置了 `a` 或 `b` 或两者，该运算符用于设置操作数的位。这意味着该位的值将设置为 1。

| A | B | A \| B |
| :--- | :--- | :--- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

**语法:**

```php
$a | $b
```

**程序:**

```php
<?php
$a = 3;
$b = 10;
echo $a | $b;
?>
```

**输出:**

```php

```