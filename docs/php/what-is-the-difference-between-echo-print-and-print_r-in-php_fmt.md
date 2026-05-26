# PHP 中的 echo、print、print_r 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-echo-print-and-print_r-in-php/](https://www.geeksforgeeks.org/what-is-the-difference-between-echo-print-and-print_r-in-php/)

## echo

`echo` 不是一种函数，而是一种语言结构。它接受参数列表（可以传递多个参数），不返回值或返回 `void`。它不能在 PHP 中用作变量函数。它用于显示传递给它的参数输出。它显示由逗号分隔的一个或多个字符串的输出。

**示例：**

```php
<?php

// PHP program to illustrate echo

// Declare variable and initialize it.
$x = "GeeksforGeeks ";
$y = "Computer science portal";

// Display the value of $x
echo $x, $y;
?>
```

**Output：**

```php
GeeksforGeeks Computer science portal
```

## print

`print` 不是真正的函数。它是一个语言构造，但总是返回值 `1`。所以可以作为一种表达式。与 `echo` 不同，`print` 一次只接受一个参数。它不能在 PHP 中用作变量函数。`print` 只输出字符串。它比 `echo` 慢。

**示例：**

```php
<?php

// PHP program to illustrate print

// Declare variable and initialize it.
$x = "GeeksforGeeks";

// Display the value of $x
print $x;
?>
```

**Output：**

```php
GeeksforGeeks
```