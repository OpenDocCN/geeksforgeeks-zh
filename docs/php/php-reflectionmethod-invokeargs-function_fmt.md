# PHP ReflectionMethod::invokeArgs() 函数

> 原文：[https://www.geeksforgeeks.org/php-reflectionmethod-invokeargs-function/](https://www.geeksforgeeks.org/php-reflectionmethod-invokeargs-function/)

`ReflectionMethod::invokeArgs()` 函数是 PHP 中的内置函数，用于调用指定的反射方法并返回该方法的结果。

## 语法

```php
mixed ReflectionMethod::invokeArgs ( $object, $parameter )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `object`：这是已初始化的类对象。
*   `parameter`：这是要传递给方法的零个或多个参数的数组。

## 返回值

此函数返回调用的方法的结果。

以下程序说明 PHP 中的 `ReflectionMethod::invokeArgs()` 函数：

## 程序示例 1

```php
<?php

// Initializing a user-defined class
class Company {

    public function GFG($name) {
        return 'GeeksforGeeks' . $name;
    }
}

// Using ReflectionMethod() over the class Company
$A = new ReflectionMethod('Company', 'GFG');

// Calling the invokeArgs() function
$B = $A->invokeArgs(new Company(),
      array(' is a Computer Science Portal.'));

// Getting the result of the invoked method.
echo $B;
?>
```

**输出：**

```php
GeeksforGeeks is a Computer Science Portal.
```

## 程序示例 2

```php
<?php

// Initializing some user-defined classes
class Department1 {

    public function hr($name) {
        return 'HR' . $name;
    }
}
class Department2 {

    public function coding($name) {
        return 'Coding' . $name;
    }
}
class Department3 {

    public function marketing($name) {
        return 'Marketing' . $name;
    }
}

// Using ReflectionMethod() over the above classes
$A = new ReflectionMethod('Department1', 'hr');
$B = new ReflectionMethod('Department2', 'coding');
$C = new ReflectionMethod('Department3', 'marketing');

// Calling the invokeArgs() function and
// getting the result of the invoked method.
echo $A->invokeArgs(new Department1(),
                      array(' is a Department.'));
echo "\n";
echo $B->invokeArgs(new Department2(),
                 array(' is also a Department.'));
echo "\n";
echo $C->invokeArgs(new Department3(),
                              array(' too.'));
?>
```

**输出：**

```php
HR is a Department.
Coding is also a Department.
Marketing too.
```

**引用：**[https://www.php.net/manual/en/reflectionmethod.invokeargs.php](https://www.php.net/manual/en/reflectionmethod.invokeargs.php)