# PHP | cosh()函数

> 原文: [https://www.geeksforgeeks.org/php-cosh-function/](https://www.geeksforgeeks.org/php-cosh-function/)

`cosh()` 函数是 PHP 中的一个内置函数，用来求一个角度的双曲余弦。
任何自变量 `arg` 的双曲余弦定义为：

（`exp(arg)` + `exp(-arg)`）/ 2

其中，`exp()` 是指数函数，并返回传递给它的参数的幂。例如 `exp(2) = e^2`。

## 语法

```php
float cosh($value)
```

## 参数

该函数接受单个参数 `$value`。它是您想要查找其双曲余弦值的数字。此参数的值必须以弧度为单位。

## 返回值

返回一个浮点数，该浮点数是作为参数传递给它的数字的双曲余弦值。

## 示例

```php
Input : cosh(3) 
Output : 10.067661995778

Input : cosh(-3)
Output : 10.067661995778

Input : cosh(2*M_PI)
Output : 267.74676148375

Input : cosh(0) 
Output : 1
```

下面用取不同值 `$value` 的程序来说明 PHP 中的 `cosh()` 函数：

*   传递 3 作为参数：

```php
<?php
echo (cosh(3));
?>
```

输出：

```
10.067661995778
```

*   传递 -3 作为参数：

```php
<?php
echo (cosh(-3));
?>
```

输出：

```
10.067661995778
```

*   当传递 `(2*M_PI)` 作为参数时，`M_PI` 是 PHP 中的一个常量，其值为 3.1415926535898：

```php
<?php
echo (cosh(2*M_PI));
?>
```

输出：

```
267.74676148375
```

*   传递 0 作为参数：

```php
<?php
echo (cosh(0));
?>
```

输出：

```
1
```

## 参考

[http://php.net/manual/en/function.cosh.php](http://php.net/manual/en/function.cosh.php)