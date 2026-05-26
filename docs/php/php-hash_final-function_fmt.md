# PHP `hash_final()` 函数

> Original: [https://www.geeksforgeeks.org/php-hash_final-function/](https://www.geeksforgeeks.org/php-hash_final-function/)

`hash_final()` 函数是 PHP 中的一个内置函数，用于完成增量散列并返回结果摘要。

## 语法

```php
hash_final( $context, $raw_output )
```

## 参数

此函数接受上述两个参数，如下所述。

*   `$context`: 此参数用于指定由 `hash_init()` 函数返回的哈希上下文。
*   `$raw_output`: 此参数用于设置布尔值。如果此参数设置为 `True`，输出包含原始二进制数据；如果参数设置为 `False`，输出包含小写十六进制。

## 返回值

此函数以小写十六进制返回包含计算出的消息摘要的字符串。

下面的程序演示了 PHP 中的 `hash_final()` 函数：

## 程序 1

```php
<?php

// PHP program too illustrate 
// hash_final function
$gfg = hash_init('md5');

hash_update($gfg, 'GeeksforGeeks A CS Portal');

// Print result return by
// hash_final function
print(hash_final($gfg));
?>
```

## 输出

```php
a26b1748ffd7e4c9923336a3c8e9a4c3
```

## 程序 2

```php
<?php

// PHP program too illustrate 
// hash_final function
$gfg = hash_init('md5');

hash_update($gfg, 'GeeksforGeeks A CS Portal');

// Print result return by
// hash_final function
print(hash_final($gfg, false));
?>
```

## 输出

```php
a26b1748ffd7e4c9923336a3c8e9a4c3
```

**引用：**[http://php.net/manual/en/function.hash-final.php#refsect1-function.hash-final-parameters](http://php.net/manual/en/function.hash-final.php#refsect1-function.hash-final-parameters)