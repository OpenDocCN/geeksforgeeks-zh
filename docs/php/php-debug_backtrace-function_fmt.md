# PHP `debug_backtrace()` 函数

> Original: [https://www.geeksforgeeks.org/php-debug_backtrace-function/](https://www.geeksforgeeks.org/php-debug_backtrace-function/)

`debug_backtrace()` 函数是 PHP 中的一个内置函数，程序员通常在调试时使用该函数。`debug_backtrace()` 函数的主要工作是生成 PHP 回溯，即检查堆栈跟踪。它返回一个由回溯 PHP 代码的关联数组组成的数组。此函数返回的所有可能元素为：

| Name | Type | Description |
| :--- | :--- | :--- |
| function | String | 调用 `debug_backtrace()` 函数的函数的名称。 |
| line | Integer | 函数调用的当前行号。 |
| file | String | 调用 `debug_backtrace()` 函数的文件名。 |
| class | String | 调用 `debug_backtrace()` 函数的类名。 |
| object | Object | 用于调用成员函数的对象名称，`debug_backtrace()` 函数存在于该成员函数中。 |
| type | String | 当前调用的类型。如果当前调用类型是方法调用，则返回 "->"。如果是静态方法调用，则返回 "::"。如果是函数调用，则不返回任何内容。 |
| args | Array | 函数定义中存在的参数列表。如果你在一个文件中使用 `debug_backtrace()` 函数，则会返回该文件包含的所有文件。例如， |

## 语法

```php
array debug_backtrace(int $options, int $limit);
```

这里，参数 `$options` 和 `$limit` 都是可选的，并且都是整型的。`$options` 参数用于位掩码，`$limit` 可用于设置要打印的堆栈帧数量限制。`$limit` 的默认值设置为零。

示例：在此示例中，我们创建了一个返回两个输入参数之和的函数，并在该函数中使用了 `debug_backtrace()` 函数。在打印输出时，首先显示输入参数的总和，然后打印代码的回溯。

## PHP

```php
<?php

function sum($a, $b) {
    echo $a + $b . "\n\n";

    var_dump(debug_backtrace());
}

sum(10, 2);

?>
```

## OUTPUT

```php
array(1) {
  [0]=>
  array(4) {
    ["file"]=>
    string(42) "/home/2228b7c9e401174a5f773007cd840e32.php"
    ["line"]=>
    int(9)
    ["function"]=>
    string(3) "sum"
    ["args"]=>
    array(2) {
      [0]=>
      int(10)
      [1]=>
      int(2)
    }
  }
}
```