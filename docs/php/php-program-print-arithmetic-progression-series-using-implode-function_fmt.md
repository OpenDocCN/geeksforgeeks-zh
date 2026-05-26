# 使用内置函数打印算术级数系列的 PHP 程序

> Original: [https://www.geeksforgeeks.org/php-program-print-arithmetic-progression-series-using-implode-function/](https://www.geeksforgeeks.org/php-program-print-arithmetic-progression-series-using-implode-function/)

我们必须用 PHP 打印两个给定数字`$a`和`$b`之间的算术级数，这两个数字都包含给定的常用算术差`$d`。

示例：

```php
Input : $a = 200, $b = 250, $d = 10
Output : 200, 210, 220, 230, 240, 250

Input : $a = 10, $b = 100, $d = 20
Output : 10, 30, 50, 70, 90
```

这个问题可以使用循环来解决，方法是从`$a`迭代到`$b`，然后将循环变量递增`$d`。但是在 PHP 中，我们也可以使用一些内置函数来解决这个特定的问题。

为此，我们必须使用以下两个函数：

*   `range()` 函数：这个函数用于在给定范围内（从低到高）创建任何类型的元素数组，例如整数、字母，即列表的第一个元素被视为低，最后一个元素被视为高。
*   `implode()` 函数：如果我们有一个元素数组，可以使用 `implode()` 函数将它们连接起来形成一个字符串。我们基本上是用字符串连接数组元素。

使用上述两个内置函数解决此问题的想法是，首先使用 `range()` 函数生成一个介于`$a`和`$b`之间的值数组，其中值递增`$d`。生成数组后，我们将使用 `implode()` 函数从数组中创建一个字符串，其中的元素将用逗号（`,`）分隔符分隔。

```php
<?php

$a = 1;
$b = 100;
$d = 15;

$arr = range($a,$b,$d);

echo implode(", ",$arr);

?>
```

帖子主题：Re：Колибри