# PHP `sin()` 函数

> 原文：[https://www.geeksforgeeks.org/php-sin-function/](https://www.geeksforgeeks.org/php-sin-function/)

三角学是数学的重要组成部分，PHP 的数学函数为我们提供了一些函数，这些函数对于涉及三角学的计算非常有用。 PHP 中的 `sin()` 函数用于查找数字的正弦值。
`sin()` 函数返回一个介于 -1 和 1 之间的浮点值，表示作为参数传递给它的角度的正弦值。 参数必须以弧度表示。

## 语法

```php
float sin ( float $value )
```

## 参数

此函数接受单个参数 `$value`。 它是您要查找其正弦值的数字。 此参数的值必须以弧度为单位。

## 返回值

它返回一个浮点数，它是作为参数传递给它的数字的正弦值。

## 示例

```php
Input : sin(3) 
Output : 0.14112000805987

Input : sin(-3)
Output : -0.14112000805987

Input : sin(2*M_PI)
Output : 1

Input : sin(0) 
Output : 0
```

下面的程序演示了 PHP 中的 `sin()` 函数：

*   传递 3 作为参数：

```php
<?php
echo (sin(3));
?>
```

产出：

```php
0.14112000805987
```

*   传递 -3 作为参数：

```php
<?php
echo (sin(-3));
?>
```

产出：

```php
-0.14112000805987
```

*   当 `(2*M_PI)` 作为参数传递时，`M_PI` 是 PHP 中的一个常量，其值为 3.1415926535898：

```php
<?php
echo (sin(2*M_PI));
?>
```

产出：

```php
1
```

*   传递 0 作为参数：

```php
<?php
echo (sin(0));
?>
```

产出：

```php
0
```

## 参考

[`http://php.net/manual/en/function.sin.php`](http://php.net/manual/en/function.sin.php)