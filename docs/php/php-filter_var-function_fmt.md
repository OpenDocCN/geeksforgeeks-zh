# PHP filter_var() 函数

> Original: [https://www.geeksforgeeks.org/php-filter_var-function/](https://www.geeksforgeeks.org/php-filter_var-function/)

函数的作用是：用指定的过滤器过滤变量。 此函数用于验证和清理数据。

## 语法

```php
filter_var(var, filtername, options)
```

## 参数

此函数接受三个参数，说明如下：

1.  `var`：必填字段。 它表示要筛选的变量。
2.  `filtername`：用于指定要使用的过滤器的 ID 或名称。 默认值为 `FILTER_DEFAULT`，这将导致不进行过滤。 可选字段。
3.  `选项`：用于指定要使用的一个或多个标志/选项。 检查每个过滤器是否有可能的选项和标志。 它也是可选字段。

## 返回值

成功时返回过滤数据，失败时返回 `False`。

以下是 `filter_var()` 函数的一些不同应用：

### Sanitize a string

在下面的示例中，我们清理一个字符串。

例如：

```php
<?php
$str = "<h1>GeeksforGeeks!</h1>";
$newstr = filter_var($str, FILTER_SANITIZE_STRING);
echo $newstr;
?>
```

输出：

```php
GeeksforGeeks!
```

### Validate an Integer

下面的示例使用 `filter_var()` 函数检查变量 `$int` 是否为整数。 如果 `$int` 是整数，下面代码的输出将是：“Integer is Valid”。 如果 `$int` 不是整数，则输出为：“Integer is not valid”：

例如：

```php
<?php
$int = 200;

if (filter_var($int, FILTER_VALIDATE_INT) === 0 || 
    !filter_var($int, FILTER_VALIDATE_INT) === false) 
{
    echo("Integer is valid");
} 
else 
{
    echo("Integer is not valid");
}
?>
```

输出：

```php
Integer is valid
```

### 验证 IP 地址

以下示例使用 `filter_var()` 函数检查变量 `$ip` 是否为有效的 IP 地址：

例如：

```php
<?php
$ip = "129.0.0.1";

if (!filter_var($ip, FILTER_VALIDATE_IP) === false) {
    echo("$ip is a valid IP address");
} else {
    echo("$ip is not a valid IP address");
}
?>
```

输出：

```php
129.0.0.1 is a valid IP address
```

### Sanitize and Validate an Email Address

以下示例使用 `filter_var()` 函数首先从 `$email` 变量中移除所有非法字符，然后检查它是否为有效的电子邮件地址：

例如：

```php
<?php
$email = "gfg@example.com";

// Remove all illegal characters from email
$email = filter_var($email, FILTER_SANITIZE_EMAIL);

// Validate e-mail
if (!filter_var($email, FILTER_VALIDATE_EMAIL) === false) {
    echo("$email is a valid email address");
} else {
    echo("$email is not a valid email address");
}
?>
```

输出：

```php
gfg@example.com is a valid email address
```

### Sanitize and Validate a URL

以下示例使用 `filter_var()` 函数首先从 URL 中移除所有非法字符，然后检查 `$url` 是否为有效的 URL：

例如：

```php
<?php
$url = "https://www.geeksforgeeks.org";

// Remove all illegal characters from a url
$url = filter_var($url, FILTER_SANITIZE_URL);

// Validate url
if (!filter_var($url, FILTER_VALIDATE_URL) === false) {
    echo("$url is a valid URL");
} else {
    echo("$url is not a valid URL");
}
?>
```

输出：

```php
https://www.geeksforgeeks.org is a valid URL
```

## 参考

[http://php.net/manual/en/function.filter-var.php](http://php.net/manual/en/function.filter-var.php)