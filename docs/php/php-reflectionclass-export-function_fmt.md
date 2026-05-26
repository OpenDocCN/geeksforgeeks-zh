# PHP ReflectionClass::export() 函数

> Original: [https://www.geeksforgeeks.org/php-reflectionclass-export-function/](https://www.geeksforgeeks.org/php-reflectionclass-export-function/)

`ReflectionClass::export()` 函数是 PHP 中的一个内置函数，用于在参数设置为 `true` 时返回字符串，否则返回 `NULL`。

**语法：**

```php
string ReflectionClass::export( mixed $argument, bool $return = FALSE)
```

**参数：** 此函数接受上述两个参数，如下所述：

*   `$parameter`: 它保存要导出的用户定义类。
*   `$return`: 它是一个布尔值，可以是 `TRUE` 或 `FALSE`。

**返回值：** 如果参数 `$return` 已设置为 `true`，则此函数以字符串形式返回，否则返回 `NULL`。

下面的程序演示了 PHP 中的 `ReflectionClass::export()` 函数：

**程序 1：**

```php
<?php

// Defining a user-defined class Company
class Company {
    public $var1 = 'GeeksforGeeks';
    public $var2 = 'GFG';

    public function type() {
        return 'Company';
    }
}

// Calling the export function
$A = ReflectionClass::export('Company', $return = TRUE);

// Getting the returned value
var_dump($A);
?>
```

发帖主题：Re：Колибри0.7.8.0

**程序 2：**

```php
<?php

// Calling the export function on inbuilt ReflectionClass
$A = ReflectionClass::export('ReflectionClass');

// Getting the returned value
var_dump($A);
?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：** [https://secure.php.net/manual/en/reflectionclass.export.php](https://secure.php.net/manual/en/reflectionclass.export.php)