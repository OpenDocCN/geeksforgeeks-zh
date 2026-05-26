# PHP `intval()` 函数

> 原文：[https://www.geeksforgeeks.org/php-intval-function/](https://www.geeksforgeeks.org/php-intval-function/)

`intval()` 函数是 PHP 中的内置函数，它返回变量的整数值。

## 语法

```php
int intval ( $var, $base )
```

## 参数

此函数接受两个参数，其中一个是必选的，另一个是可选的。参数说明如下：

*   `$var`：必需参数，用作需要转换为整数值的变量。
*   `$base`：可选参数，指定将 `$var` 转换为其对应整数的进制。如果未指定 `$base`：
    *   如果 `$var` 包含 `0x`（或 `0X`）作为前缀，则进制为 16。
    *   如果 `$var` 以 `0` 开头，则进制为 8。
    *   否则，进制为 10。

## 返回值

返回 `$var` 对应的整数值。

## 示例

```php
Input : $var = '120', $base = 8
Output : 80

Input : $var = 0x34
Output : 52

Input : $var = 034
Output : 28
```

以下程序说明了如何在 PHP 中使用 `intval()` 函数：

### 程序 1

```php
<?php
$var = '7.423';
$int_value = intval($var);
echo $int_value;
?>
```

**输出：**

```php
7
```

### 程序 2

```php
<?php
$var = 0x423;
$int_value = intval($var);
echo $int_value;
?>
```

**输出：**

```php
1059
```

### 程序 3

```php
<?php
$var = "64";
echo intval($var)."\n".intval($var, 8);
?>
```

**输出：**

```php
64
52
```

**引用：**[http://php.net/manual/en/function.intval.php](http://php.net/manual/en/function.intval.php)