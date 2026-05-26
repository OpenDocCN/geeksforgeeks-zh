# PHP ReflectionMethod getModifiers() 函数

> Original: [https://www.geeksforgeeks.org/php-reflectionmethod-getmodifiers-function/](https://www.geeksforgeeks.org/php-reflectionmethod-getmodifiers-function/)

`ReflectionMethod::getModifiers()` 函数是 PHP 中的一个内置函数，用于返回方法修饰符的数字表示形式。

**语法：**

```php
int ReflectionMethod::getModifiers( void )
```

**参数：** 此函数不接受任何参数。

**返回值：** 此函数返回方法修饰符的数字表示形式。

以下程序说明 PHP 中的 `ReflectionMethod::getModifiers()` 函数：

**程序 1：**

```php
<?php

// Initializing a user-defined class
class Company {

    protected function GeeksforGeeks($name) {
        return 'GFG' . $name;
    }
}

// Using ReflectionMethod() over the class Company
$A = new ReflectionMethod(new Company(), 'GeeksforGeeks');

// Calling the getModifiers() function
$B = $A->getModifiers();

// Getting the numeric representation 
// of the method modifiers.
var_dump($B);
?>
```

**输出：**

```php
int(134283776)
```

**程序 2：**

```php
<?php

// Initializing a user-defined class
class Department
{
    final public static function Coding()
    {
        return;
    }
    public function Marketing()
    {
        return;
    }
}

// Using ReflectionMethod() over the above class
$A = new ReflectionMethod('Department', 'Coding');
$B = new ReflectionMethod('Department', 'Marketing');

// Calling the getModifiers() function and 
// getting the numeric representation 
// of the above method modifiers.
var_dump($A->getModifiers());
var_dump($B->getModifiers());
?>
```

**输出：**

```php
int(134217989)
int(134283520)
```

**引用：** [https://www.php.net/manual/en/reflectionmethod.getmodifiers.php](https://www.php.net/manual/en/reflectionmethod.getmodifiers.php)