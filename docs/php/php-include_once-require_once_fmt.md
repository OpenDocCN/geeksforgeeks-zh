# PHP | include_once() 和 require_once()

> 原文：[https://www.geeksforgeeks.org/php-include_once-require_once/](https://www.geeksforgeeks.org/php-include_once-require_once/)

我们已经在文章 [PHP | Include And Require](https://www.geeksforgeeks.org/php-inclusion/) 中了解了 PHP 中的文件包含。在上一篇文章中，我们已经讨论了用于文件包含的 `include()` 和 `require()` 函数。在本文中，我们将讨论 PHP 中另外两个用于文件包含的函数：`include_once()` 和 `require_once()` 函数。

## include_once() 函数

当您可能需要多次包含被调用的文件时，可以使用 `include_once()` 函数将一个 PHP 文件包含在另一个文件中。如果发现已包含该文件，则调用脚本将忽略进一步的包含。

如果名为 `a.php` 的文件是使用 `include_once()` 函数调用 `b.php` 的 PHP 脚本，并且没有找到 `b.php`，则 `a.php` 会执行并发出警告，但不包括在 `b.php` 中编写的代码部分。

**语法：**

```php
include_once('name of the called file with path');
```

**示例：**

```php
// name of file is header.inc.php
<?php
echo "GEEKSFORGEEKS";
?>
```

上面的文件是 `header.inc.php`。

上面的文件 `header.inc.php` 在下面的文件 `index.php` 中使用 `include_once()` 函数包含了两次。但是从输出中，您会发现第二个 Include 实例被忽略了，因为 `include_once()` 函数忽略了第一个实例之后的所有相似的 Include。

```php
// name of file is index.php
<?php
include_once('header.inc.php');
include_once('header.inc.php');
?>
```

## require_once() 函数

当您可能需要多次包含被调用的文件时，可以使用 `require_once()` 函数将一个 PHP 文件包含在另一个 PHP 文件中。如果发现已包含该文件，则调用脚本将忽略进一步的包含。

如果 `a.php` 是用 `require_once()` 函数调用 `b.php` 的 PHP 脚本，但没有找到 `b.php`，则 `a.php` 会停止执行，导致致命错误。

**语法：**

```php
require_once('name of the called file with path');
```

**示例：**

```php
// name of file is header.inc.php
<?php
echo "GEEKSFORGEEKS";
?>
```

上面的文件是 `header.inc.php`。

上面的文件 `header.inc.php` 在下面的 `index.php` 文件中包含了两次，函数名为 `require_once()`。但是从输出中，您会发现第二个 Include 实例被忽略了，因为 `require_once()` 函数忽略了第一个实例之后的所有相似的 Include。

```php
// name of file is index.php
<?php
require_once('header.inc.php');
require_once('header.inc.php');
?>
```

## include_once() 与 require_once()

这两个函数的工作方式相同，产生的输出也相同，但如果出现任何错误，则会出现差异。

**示例：**

如果我们没有名为 `header.inc.php` 的文件，那么在 `include_once()` 的情况下，输出将显示有关缺少文件的警告，但至少会显示 `index.php` 文件的输出。

在 `require_once()` 的情况下，如果 PHP 文件丢失，则会出现致命错误，不会显示任何输出，并且执行会暂停。