# PHP gethostbyaddr()函数

> Original: [https://www.geeksforgeeks.org/php-gethostbyaddr-function/](https://www.geeksforgeeks.org/php-gethostbyaddr-function/)

`gethostbyaddr()`函数是 PHP 中的一个内置函数，它返回指定 IP 地址的域名。

## 语法

```php
gethostbyaddr($ip_address);
```

## 参数

此函数接受一个参数，如上所述，如下所述：

*   `$ip_address`：必需参数。它指定要查找主机名的 IP 地址。以字符串形式传递。

## 返回值

*   此函数在成功时返回主机名，在失败时返回 IP 地址。

## 注

*   此函数适用于 PHP 4.0.0 及更新版本。

## 示例

```php
<?php
$host = gethostbyaddr("52.25.109.230");
echo $host;
?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：**[https://www.php.net/manual/en/function.gethostbyaddr.php](https://www.php.net/manual/en/function.gethostbyaddr.php)