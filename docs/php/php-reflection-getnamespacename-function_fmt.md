# PHP：反射 `getNamespaceName()` 函数

> Original: `https://www.geeksforgeeks.org/php-reflection-getnamespacename-function/`

`Reflection::getNamespaceName()` 函数是 PHP 中的内置函数，用于返回指定名称空间的名称。

**语法：**

```php
string Reflection::getNamespaceName( void )
```

**参数：** 此函数不接受任何参数。

**返回值：** 此函数返回指定命名空间的名称。

以下程序说明 PHP 中的 `Reflection::getNamespaceName()` 函数：

**程序 1：**

```php
<?php

// Defining a namespace and class GFG
namespace A\B;
class GFG{ }

// Using ReflectionClass over the namespace and
// specified class GFG
$ReflectionClass = new \ReflectionClass('A\\B\\GFG');

// Calling getNamespaceName() function
$A = $ReflectionClass->getNamespaceName();

// Getting the name of the specified namespace
var_dump($A);
?>
```

**Output:**

```php
string(3) "A\B"
```

**程序 2：**

```php
<?php

// Using ReflectionClass over the inbuilt class 'ReflectionClass'
$ReflectionClass = new ReflectionClass('ReflectionClass');

// Calling getNamespaceName() function
$A = $ReflectionClass->getNamespaceName();

// Getting the name of the namespace
var_dump($A);
?>
```

**Output:**

```php
string(0) ""
```

**引用：** `https://www.php.net/manual/en/reflectionclass.getnamespacename.php`