# PHP `hash_hmac()` 函数

> Original: [https://www.geeksforgeeks.org/php-hash_hmac-function/](https://www.geeksforgeeks.org/php-hash_hmac-function/)

`hash_hmac()` 函数是 PHP 中的一个内置函数，用于使用 HMAC 方法生成带键的散列值。

## 语法

```php
string hash_hmac( $algo, $msg, $key, $raw_opt )
```

## 参数

此函数接受上述四个参数，如下所述。

*   `$algo`：它是必需的参数，用于指定所选的散列算法，例如 "MD5"、"sha256"、"sha1"。
*   `$msg`：此参数用于保存要散列的消息。
*   `$key`：此参数用于指定用于生成消息摘要的 HMAC 变体的共享密钥。
*   `$raw_opt`：此参数用于保存布尔值。如果设置为 `True`，则返回原始二进制数据；如果设置为 `False`，则返回输出小写十六进制。

## 返回值

此函数以小写十六进制返回包含计算出的消息摘要的字符串。

## 示例

以下程序说明 PHP 中的 `hash_hmac()` 函数：

### 程序 1

```php
<?php

// PHP program to illustrate
// the hash_hmac function
echo hash_hmac('md5', 
'GeeksforGeeks A Computer Science Portal',
                                'GFG_DATA');
?>
```

### 输出

```php
65f3fc3c9085077f44ade6ce2d21eba4
```

### 程序 2

```php
<?php

// PHP program to illustrate
// the hash_hmac function
echo hash_hmac('md5', 
'GeeksforGeeks A Computer Science Portal',
                                'GFG_DATA', false). "\n";
echo hash_hmac('md5', 
'GeeksforGeeks A Computer Science Portal',
                                'GFG_DATA', true);                                 
?>
```

### 输出

```php
65f3fc3c9085077f44ade6ce2d21eba4
eóüd­æî-!ë¤ < pre>?d­æî-!ë¤>
```

## 引用

[http://php.net/manual/en/function.hash-hmac.php](http://php.net/manual/en/function.hash-hmac.php)