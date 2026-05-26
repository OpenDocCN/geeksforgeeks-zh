# PHP ReflectionParameter::allowsNull() 函数

> 原文：[https://www.geeksforgeeks.org/php-reflectionparameter-allowsnull-function/](https://www.geeksforgeeks.org/php-reflectionparameter-allowsnull-function/)

## 函数介绍

`ReflectionParameter::allowsNull()` 函数是 PHP 中的内置函数，用于检查是否允许参数为 `NULL`。

## 语法

```php
bool ReflectionParameter::allowsNull ( void )
```

## 参数

此函数不接受任何参数。

## 返回值

如果允许 `NULL` 参数，则此函数返回 `TRUE`，否则返回 `FALSE`。

## 示例程序

### 程序 1

以下程序说明了 PHP 中的 `ReflectionParameter::allowsNull()` 函数：

```php
<?php

// Initializing a user-defined class Company1
class Company1
{
    public function GFG( Exception $Parameter){}
}

// Initializing a subclass Company2
class Company2 extends Company1
{
}

// Using the ReflectionParameter over the above class
$A = new ReflectionParameter(['Company2', 'GFG'], 0);

// Calling the allowsNull() function
$B = $A->allowsNull();

// Getting the boolean value TRUE if NULL 
// parameter is allowed else FALSE.
var_dump($B);
?>
```

**输出：**

```php
bool(false)
```

### 程序 2

```php
<?php

// Initializing some user-defined classes
class Department1
{
    public function HR($Parameter1){}
}
class Department2
{
    public function Coding( Exception $Parameter2, Exception $Parameter3){}
}
class Department3
{
    public function Marketing($Parameter4, $Parameter5, $Parameter6){}
}

// Using the ReflectionParameter over the above classes
$A = new ReflectionParameter(['Department1', 'HR'], 0);
$B = new ReflectionParameter(['Department2', 'Coding'], 1);
$C = new ReflectionParameter(['Department3', 'Marketing'], 2);

// Calling the allowsNull() function and
// getting the boolean value TRUE if NULL 
// parameter is allowed else FALSE.
var_dump($A->allowsNull());
var_dump($B->allowsNull());
var_dump($C->allowsNull());
?>
```

**输出：**

```php
bool(true)
bool(false)
bool(true)
```

## 引用

[https://www.php.net/manual/en/reflectionparameter.allowsnull.php](https://www.php.net/manual/en/reflectionparameter.allowsnull.php)