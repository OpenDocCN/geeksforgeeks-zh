# PHP `gmp_clrbit()` 函数

> Original: [https://www.geeksforgeeks.org/php-gmp_clrbit-function/](https://www.geeksforgeeks.org/php-gmp_clrbit-function/)

`gmp_clrbit()` 函数是 PHP 中的一个内置函数，它清除一个 GMP 编号[(GNU Multiple Precision)](https://en.wikipedia.org/wiki/GNU_Multiple_Precision_Arithmetic_Library)中的一位。函数的作用是：将 GMP 编号中指定`索引`处的位设置为`0`。索引从最低有效位开始从零开始。

## 语法

```php
gmp_clrbit( $num, $index )
```

## 参数

该函数接受两个必选参数`$num`和`$index`，如上面的语法所示。 这些参数是：

*   `$num`: 在 PHP 5.5 中可以是 GMP 编号资源，在 PHP 5.6 及更高版本中可以是 GMP 对象，或者你可以向函数传递数字字符串，前提是你能将这些字符串转换为数字。
*   `$index`: 要清除的位的索引。索引从 0 开始，其中索引 0 表示最低有效位。

## 返回值

此函数返回 GMP 编号（在 PHP 5.5 和更早版本中）或 GMP 对象（在 PHP 5.6 和更高版本中），它是指定索引处的位设置为 0 后形成的数字。

## 示例

```
Input : $num = 255, $index = 0
Output : 254

Input : $num = 128, $index = 7
Output : 0
```

以下程序说明了 `gmp_clrbit()` 函数：

### 程序 1

```php
<?php
// PHP program to illustrate
// gmp_clrbit() function
$num = gmp_init(255);

gmp_clrbit($num, 0); // index starts at 0, least significant bit

echo gmp_strval($num);
?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php
// PHP program to illustrate
// gmp_clrbit() function
$num = gmp_init("314567128");

gmp_clrbit($num, 8); // index starts at 0, least significant bit

echo gmp_strval($num);
?>
```

发帖主题：Re：Колибри0.7.8.0

## 引用

`http://php.net/manual/en/function.gmp-clrbit.php`