# PHP `gmp_random()` 函数

> Original: [https://www.geeksforgeeks.org/php-gmp_random-function/](https://www.geeksforgeeks.org/php-gmp_random-function/)

`gmp_random()` 函数是 PHP 中的一个内置函数，可生成随机数。随机数的范围将在 0 和每个肢体的位数之间（肢体是内部 GMP 机制。分支中的位数不是静态的，它可以随系统的不同而不同。通常，肢体中的位数为 16 或 32，但情况并不总是如此。）乘以限制器。生成的数字取决于限制器，即如果限制器为负数，则生成的数也将为负数。

## 语法

```php
GMP gmp_random ( int $limiter )
```

## 参数

`gmp_random()` 函数接受单个参数，如下所示：

*   **`$limiter`**: 这是 `gmp_random()` 函数接受的唯一必需参数。此参数设置限制器值。此参数可以是 PHP 5.5 及更早版本中的 GMP 资源，PHP 5.6 及更高版本中的 GMP 对象，或者您可以传递一个数字字符串，前提是该字符串可以转换为数字。

## 返回值

如上所述，此函数返回一个介于零和每个肢体的位数之间的随机数。

下面的程序演示了 PHP 中的 `gmp_random()` 函数。

## 程序 1

```php
<?php
// php code implementing gmp_random() function

// random number from 0 to 1 * bits per limb
$rand = gmp_random(1); 
echo gmp_strval($rand) . "\n";

?>
```

帖子主题：Re：Колибри

## 程序 2

```php
<?php
// php code implementing gmp_random() function

// random number from 0 to 2 * bits per limb
$rand = gmp_random(2); 
echo gmp_strval($rand) . "\n";

?>
```

帖子主题：Re：Колибри

## 相关文章

*   [PHP GMP](https://www.geeksforgeeks.org/tag/php-gmp/)
*   [PHP|GMP_RANDOM_RANGE()11-13](https://www.geeksforgeeks.org/php-gmp_random_range-function/)
*   [PHP|GMP_RANDOM_BITS()11-13](https://www.geeksforgeeks.org/php-gmp_random_bits-function/)

## 引用

[http://php.net/manual/en/function.gmp-random.php](http://php.net/manual/en/function.gmp-random.php)