# 如何在 PHP 中启动和停止定时器？

> 原文：[https://www.geeksforgeeks.org/how-to-start-and-stop-a-timer-in-php/](https://www.geeksforgeeks.org/how-to-start-and-stop-a-timer-in-php/)

您可以使用 PHP 中的 [`microtime()`](https://www.geeksforgeeks.org/php-microtime-function/) 函数来启动和停止 PHP 中的计时器。`microtime()` 函数是 PHP 中的一个内置函数，用于以微秒为单位返回当前的 Unix 时间戳。

在本文中，您将学习 `microtime()` 函数的用法。

## 语法

```php
microtime( $get_as_float )
```

*   **参数：** `$get_as_float` 作为参数传递给 `microtime()` 函数，默认返回字符串格式的微秒时间。
*   **返回值：** 默认情况下，`microtime()` 函数以字符串形式返回时间，但如果设置为 `TRUE`，则返回浮点数形式的时间。默认值是 `FALSE`。

## 示例 1

以下示例使用 `false` 作为 `microtime()` 方法的参数。

```php
<?php

// Displaying the micro time as a string
  echo ("Displaying the micro time as a string :");
  echo(microtime());
?>
```

**输出**

```
Displaying the micro time as a string :0.62248800 1620222618
```