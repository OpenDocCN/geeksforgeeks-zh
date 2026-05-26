# PHP 中 `$var` 和 `$$var` 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-var-and-var-in-php/](https://www.geeksforgeeks.org/difference-between-var-and-var-in-php/)

在 PHP 中，`$var` 用于存储整型、字符串、布尔型、字符型等变量的值。`$var` 是一个变量，`$$var` 将变量的值存储在其中。

**有:** 有

**语法:**
```php
$variable = value;
```
*   `$variable` 是变量名
*   `value` 是变量的初始值。

**示例 1:** 本示例使用 `$var`，存储和显示值。

### 示例 1

```php
<?php

// String value
$value1 = "hello Geeks";

// Display string value
echo $value1;
echo "<br/>";

// Boolean value
$value2 = true;

// Display boolean value
echo $value2;
echo "<br/>";

// Integer value
$value3 = 34;

// Display integer value
echo $value3;
echo "<br/>";
?>
```

**Output**
```php
hello Geeks<br/>1<br/>34<br/>
```

**`$$var`:** `$$var` 将 `$variable` 的值存储在其中。

**语法:**
```php
$variable = "value";
$variable = "new_value";
```
*   `$variable` 是值为 `value` 的初始变量。
*   `$variable` 用于保存另一个值。

我们可以通过使用第一个变量的 `$value` 获得另一个值。

**示例 2:** PHP 程序演示 `$$var`。

### 示例 2

```php
<?php

// String value
$value1 = "hello";

// Display string value
echo $value1;

echo "\n";

// Store another string in $var
$value1 = "Hello php";

// Access another string using
// value of $var
echo "$value1";
?>
```

**Output**
```php
hello
Hello php
```

**两者的区别:** 变量 `$var` 用于存储变量的值，变量 `$$var` 用于存储变量的引用。