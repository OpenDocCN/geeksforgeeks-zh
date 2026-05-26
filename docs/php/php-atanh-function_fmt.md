# PHP | atanh()函数

> 原文: [https://www.geeksforgeeks.org/php-atanh-function/](https://www.geeksforgeeks.org/php-atanh-function/)

在数学中，反双曲函数是双曲函数的反函数。对于双曲函数的给定值，相应的反双曲函数提供相应的双曲角。PHP 为我们提供了反双曲计算的内置函数。PHP 中的 `atanh()` 函数用于查找作为参数传递给它的数字的反双曲正切值。

## 语法

```php
float atanh($value)
```

## 参数

该函数接受单个参数 `$value`。它是您想要查找其反双曲正切值的数字。此参数的值必须以弧度为单位。

## 返回值

它返回一个浮点数，该浮点数是作为参数传递给它的一个数的反双曲正切值。

## 示例

```php
Input : atanh(0.50)  
Output : 0.54930614433405

Input : atanh(-0.50) 
Output : -0.54930614433405

Input : atanh(1)
Output : INF

Input : atanh(M_PI_4) 
Output : 1.0593061708232
```

在下面的程序中，取参数 `$value` 的不同值用来说明 PHP 中的 `atanh()` 函数：

*   传递 0.50 作为参数：

```php
<?php
echo (atanh(0.50));
?>
```

输出：

```
0.54930614433405
```

*   传递 -0.50 作为参数：

```php
<?php
echo (atanh(-0.50));
?>
```

输出：

```
-0.54930614433405
```

*   传递 1 作为参数：

```php
<?php
echo (atanh(1));
?>
```

输出：

```
INF
```

*   当 `M_PI_4` 作为参数传递时，`M_PI_4` 是 PHP 中的一个常量，其值为 0.78539816339744830962：

```php
<?php
echo (atanh(M_PI_4));
?>
```

输出：

```
1.0593061708232
```

## 参考

[http://php.net/manual/en/function.atanh.php](http://php.net/manual/en/function.atanh.php)