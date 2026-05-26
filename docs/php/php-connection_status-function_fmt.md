# connection_status() 函数

> 原文: `https://www.geeksforgeeks.org/php-connection_status-function/`

`connection_status()` 函数是 PHP 中的一个内置函数，返回当前的连接状态。

**语法:**

```php
int connection_status( void )
```

**参数:** 此函数不接受任何参数。

**返回值:** 该函数返回连接状态位域。返回的连接状态位域的可能值为:

*   `0`: CONNECTION_NORMAL – 正常运行
*   `1`: CONNECTION_ABORTED – 被用户或网络错误中止
*   `2`: CONNECTION_TIMEOUT – 超时
*   `3`: CONNECTION_ABORTED & CONNECTION_TIMEOUT – 中止并超时

**注意:** 此函数适用于 PHP 4.0.0 及更新版本。

下面的程序说明了 PHP 中的 `connection_status()` 函数。

**程序 1:**

```php
<?php

switch (connection_status()) {
    case CONNECTION_ABORTED:
        echo 'Connection aborted';
        break;
    case CONNECTION_TIMEOUT:
        echo 'Connection timed out';
        break;
    case CONNECTION_NORMAL:
        echo 'Connection is in a normal state';
        break;
    case (CONNECTION_ABORTED & CONNECTION_TIMEOUT):
        echo 'Connection aborted and timed out';
        break;
    default:
        echo 'Unknown';
        break;
}
?>
```

**输出:**

```
Connection is in a normal state
```

**程序 2:** 在浏览器中断或关闭的情况下，一些输出将被发送到浏览器以供 `connection_status()` 工作。

```php
<?php

// This will work even if browser breaks or closed
// Sending this to client's browser
switch (connection_status()) {
    case CONNECTION_ABORTED:
        echo 'Connection aborted';
        break;
    case CONNECTION_TIMEOUT:
        echo 'Connection timed out';
        break;
    case CONNECTION_NORMAL:
        echo 'Connection is in a normal state';
        break;
    case (CONNECTION_ABORTED & CONNECTION_TIMEOUT):
        echo 'Connection aborted and timed out';
        break;
    default:
        echo 'Unknown';
        break;
}
?>
```

**输出:**

```
Connection is in a normal state
```

**参考:** `https://www.php.net/manual/en/function.connection-status.php`