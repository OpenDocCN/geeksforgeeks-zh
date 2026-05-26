# PHP 中 `die()` 和 `exit()` 函数的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-die-and-exit-functions-in-php/](https://www.geeksforgeeks.org/difference-between-die-and-exit-functions-in-php/)

## PHP `exit()` 函数

在 PHP 中，`exit()` 函数打印一条消息并退出应用程序。它通常用于在出现错误时打印不同的消息。当没有错误并且必须停止执行时，使用`exit()`。

**语法:**

```php
exit("Message goes here");
or
exit();
```

**示例:**

```php
exit("This request is processed");
```

**程序 1:**

```php
<?php
   exit ("This is an exit function in php");
   echo "This will not printed because "
    . "we have executed exit function";
?>
```

**输出:**

```php
This is an exit function in php
```

**程序 2:**

```php
<?php
  $a = 10;
  $b = 10.0;
  if($a == $b) {
    exit('variables are equal');
  }
  else {
    exit('variables are not equal'); 
  }
?>
```

**输出:**

```php
variables are equal
```

## PHP `die()` 函数

在 PHP 中，`die()` 同`exit()`。程序的结果将是一个空屏幕。出现错误必须停止执行时，使用 `die()`。

**语法:**

```php
die("Message goes here"); 
or 
die();
```

**示例:**

```php
die('Oops! Something went wrong');
```

**程序:**

```php
<?php
    $num = 1;

// die can only print string values,
    // hence there will be no output
    die($num);
?>
```

**输出:**

```php
No Output
```

**注意:** 上述程序的输出将是一个空屏幕，因为它类似于`exit()`，`die()`只能打印字符串值。

## `die()` 和 `exit()` 的区别函数

| **die()** | **exit()** |
| --- | --- |
| The die () method is used to throw an exception | The exit () method is only used to exit the process. |
| The die () function is used to print messages. | The exit () method exits the script or can be used to print alternative messages. |
| This method starts with die () in Perl. | This method is from C. |