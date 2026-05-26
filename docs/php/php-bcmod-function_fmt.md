# PHP | bcmod()函数

> 原文: [https://www.geeksforgeeks.org/php-bcmod-function/](https://www.geeksforgeeks.org/php-bcmod-function/)

PHP 中的 `bcmod()` 函数是一个内置函数，用于计算任意精度数字的模。该函数接受任意精度的数字，并在将结果缩放到指定精度后返回该数字的模。

## 语法

```php
string bcmod ( string $dividend, string $modulus [, int $scale ] )
```

## 参数

该函数接受两个必需参数和一个可选参数，解释如下：

*   `$dividend`：代表被除数的字符串。
*   `$modulus`：代表模数的字符串。
*   `$scale`（可选）：类型为 `int`，用于指定结果的小数位数。

## 返回值

当 `$dividend` 除以 `$modulus` 时，该函数返回余数。换句话说，它返回的值相当于 `$dividend % $modulus`。如果 `$modulus` 为零，则该函数返回 `NULL`。

## 示例

```php
Input:  $dividend = 11, $modulus = 3
Output: 2

Input:  $dividend = 3, $modulus = 11
Output: 3
```

下面的程序说明了 PHP 中的 `bcmod()` 函数：

### 程序 1

```php
<?php
// PHP program to illustrate bcmod() function

// input numbers with arbitrary precision
$dividend = "11";
$modulus = "3";

// calculates the modulus
$res = bcmod($dividend, $modulus);

echo $res;

?>
```

输出：

```
2
```

### 程序 2

```php
<?php
// PHP program to illustrate bcmod() function

// input numbers with arbitrary precision
$dividend = "3";
$modulus = "11";

// calculates the modulus
$res = bcmod($dividend, $modulus);

echo $res;

?>
```

输出：

```
3
```

## 参考

[http://php.net/manual/en/function.bcmod.php](http://php.net/manual/en/function.bcmod.php)