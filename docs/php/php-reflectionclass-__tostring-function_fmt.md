# PHP ReflectionClass::__toString() 函数

> Original: [https://www.geeksforgeeks.org/php-reflectionclass-__tostring-function/](https://www.geeksforgeeks.org/php-reflectionclass-__tostring-function/)

`ReflectionClass::__toString()` 函数是 PHP 中的内置函数，用于返回指定 `ReflectionClass` 对象的字符串表示形式。

**语法：**
```php
string ReflectionClass::__toString ( void )
```

**参数：** 此函数不接受任何参数。
**返回值：** 此函数返回指定 `ReflectionClass` 对象的字符串表示形式。

以下程序说明 PHP 中的 `ReflectionClass::__toString()` 函数：

**程序 1：**
```php
<?php

// Creating a user-defined function
class Alphabets {
    public function A() {}
    public function B() {}
}

// Using ReflectionClass() over the 
// class Alphabets
$class = new ReflectionClass('Alphabets');

// Calling the __toString() function
$A = $class->__toString();

// Getting the string representation
var_dump($A);
?>
```

发帖主题：Re：Колибри0.7.0

> String(435) "Class [ <user> class Alphabets ] { @@/home/829bc146b7074eafd150c8e57aee5445.php 4-7 - Constants [0] {11} - Static Properties [0] {11} - Static Methods [0] {11} - Properties [0] {9} - Methods [2] { Method [ <user> public method A ] {@/home/829bc146b7074eafd150c8e57aee5445.php 5-5} Method [ <user> public method B ] {@/home/829bc146b7074eafd150c8e57aee5445.php 6-6} } }"

**程序 2：**
```php
<?php

// Using ReflectionClass()
$class = new ReflectionClass('ReflectionClass');

// Calling the __toString() function
$A = $class->__toString();

// Getting the string representation
var_dump($A);
?>
```

发帖主题：Re：Колибри0.7.0

> String(6824) "Class [ <reflection> class ReflectionClass implements Reflector ] { - Constants [3] { Constant [ INTEGER IS_IMPLICIT_ABSTRACT ] {16} Constant [ INTEGER IS_EXPLICIT_ABSTRACT ] {32} Constant [ INTEGER IS_FINAL ] {4} } - Static Properties [0] { } - Static Methods [1] { Method [ <reflection prototype=\"Reflector\"> static public method export ] { - Parameters [2] { Parameter #0 [ <required> $argument ] Parameter #1 [ <optional> $return ] } - Returns [ VOID ] } } - Properties [0] { } - Methods [71] { Method [ <reflection> public method getShortName ] { - Parameters [0] { } - Returns [ STRING ] } ... } }"

**引用：** [https://www.php.net/manual/en/reflectionclass.tostring.php](https://www.php.net/manual/en/reflectionclass.tostring.php)