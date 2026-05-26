# PHP `acosh()` 函数

> 原文: [https://www.geeksforgeeks.org/php-acosh-function/](https://www.geeksforgeeks.org/php-acosh-function/)

在数学中，反双曲函数是双曲函数的反函数。对于双曲函数的给定值，相应的反双曲函数提供相应的双曲角。PHP 为我们提供了逆超光速计算的内置函数。PHP 中的 `acosh()` 函数用于查找作为参数传递给它的数字的反双曲余弦。

## 语法

```php
float acosh($value)
```

## 参数

该函数接受单个参数 `$value`。它是您想要查找其反双曲余弦值的数字。此参数的值必须以弧度为单位。

## 返回值

它返回一个浮点数，该浮点数是作为参数传递给它的一个数的反双曲余弦值。

## 示例

```php
Input : acosh(7)
Output : 2.6339157938496

Input : acosh(56)
Output : 4.7184191423729

Input : acosh(2.45)
Output : 1.5447131178707
```

在下面的程序中，取不同的值 `$value` 用来说明 PHP 中的 `acosh()` 函数：

*   传递 7 作为参数：

```php
<?php
echo (acosh(7));
?>
```

输出：

```php
2.6339157938496
```

*   传递 56 作为参数：

```php
<?php
echo (acosh(56));
?>
```

输出：

```php
4.7184191423729
```

*   传递 2.45 作为参数：

```php
<?php
echo (acosh(2.45));
?>
```

输出：

```php
1.5447131178707
```

## 参考

[http://php.net/manual/en/function.acosh.php](http://php.net/manual/en/function.acosh.php)