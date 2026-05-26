# PHP

## getprotobyname()函数

> Original: [https://www.geeksforgeeks.org/php-getprotobyname-function/](https://www.geeksforgeeks.org/php-getprotobyname-function/)

`getprotobyname()`函数的作用是：它是 PHP 中的一个内置函数，它返回指定协议名的协议号。

**语法：**

```php
int getprotobyname( string $name )
```

**参数：** 此函数接受必需的单个参数 `$name`。它指定协议名称，如 `TCP`、`ICMP`、`UDP`、`IP` 等。

**返回值：** 此函数成功时返回协议号，失败时返回 `False`。

**注意：** 此函数适用于 `PHP 4.0.0` 及更新版本。

下面的程序演示了 PHP 中的 `getprotobyname()`函数：

**程序 1：** 此程序获取协议名“`TCP`”的协议号。

```php
<?php

// Use getprotobyname() function to 
// get the protocol number
$protocolnum = getprotobyname("tcp");

// Display the result
echo $protocolnum;

?>
```

**程序 2：** 该程序检查许多协议名称。

```php
<?php

$protocols = array("tcp", "udp", "hmp", "ipv6");

foreach( $protocols as $protocol ){

// Use getprotobyname() function to 
    // get the protocol number
    $protocol_name = getprotobyname($protocol);

// Display the result
    echo $protocol_name . ": " . $protocol . "<br>";
}
?>
```

**引用：** [https://www.php.net/manual/en/function.getprotobyname.php](https://www.php.net/manual/en/function.getprotobyname.php)