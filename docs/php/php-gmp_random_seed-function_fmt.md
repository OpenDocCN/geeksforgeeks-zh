# PHP `gmp_random_seed()` 函数

> Original: [https://www.geeksforgeeks.org/php-gmp_random_seed-function/](https://www.geeksforgeeks.org/php-gmp_random_seed-function/)

`gmp_random_seed()` 是 PHP 中的一个内置函数，用于设置 RNG 种子（[随机数生成](https://en.wikipedia.org/wiki/Random_number_generation)）。

## 语法

```php
void gmp_random_seed ( mixed $seed )
```

## 参数

`gmp_random_seed()` 函数接受如上所述的单个参数，如下所述：

*   **`$seed`**：这是 `gmp_random_seed()` 函数所需的参数，用于为 [`gmp_random()`](http://php.net/manual/en/function.gmp-random.php)、[`gmp_random_range()`](http://php.net/manual/en/function.gmp-random-range.php) 和 [`gmp_random_bits()`](http://php.net/manual/en/function.gmp-random-bits.php) 函数设置种子。此参数在 PHP 5.5 及更早版本中可以是 GMP 资源，在 PHP 5.6 及更高版本中可以是 GMP 对象，或者您可以传递一个数字字符串，前提是该字符串可以转换为数字。

## 返回值

函数 `gmp_random_seed()` 成功时返回 `NULL`，失败时返回 `FALSE`。

## 注

```php
Warning: The function generates an E_WARNING and returns FALSE if the seed is not valid.
```

## 示例

下面的程序说明了 PHP 中的 `gmp_random_seed()` 函数：

### 程序 1

```php
<?php

// PHP code implementing the gmp_random_seed function

// setting the seed
gmp_random_seed(100);

var_dump(gmp_strval(gmp_random(1)));

?>
```

帖子主题：Re：Колибри

### 程序 2

```php
<?php
//php code implementing the gmp_random_seed() function

// set the seed to something else
gmp_random_seed(gmp_init(-100));

var_dump(gmp_strval(gmp_random_bits(10)));

?>
```

帖子主题：Re：Колибри

### 程序 3

```php
<?php
//PHP code implementing gmp_random_seed() function

// set the seed to something invalid
var_dump(gmp_random_seed('not a number'));

?>
```

帖子主题：Re：Колибри

## 相关文章

*   [php|gmp_mod()函数](https://www.geeksforgeeks.org/php-gmp_mod-function/)
*   [php|gmp_random_range()函数](https://www.geeksforgeeks.org/php-gmp_random_range-function/)

## 引用

[http://php.net/manual/en/function.gmp-random-seed.php](http://php.net/manual/en/function.gmp-random-seed.php)