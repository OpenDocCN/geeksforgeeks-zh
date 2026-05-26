# PHP ReflectionProperty::__toString() 函数

> Original: [https://www.geeksforgeeks.org/php-reflectionproperty-__tostring-function/](https://www.geeksforgeeks.org/php-reflectionproperty-__tostring-function/)

## 函数介绍
`ReflectionProperty::__toString()` 函数是 PHP 中的内置函数，用于返回指定属性的字符串形式。

## 语法
```php
public string ReflectionProperty::__toString ( void ) : string
```

## 参数
此函数不接受任何参数。

## 返回值
此函数返回指定属性的字符串形式。

## 示例程序
以下程序说明 PHP 中的 `ReflectionProperty::__toString()` 函数：

### 程序 1
```php
<?php

// Initializing a user-defined class Company
class Company
{
    private $SizeOfGeeksforGeeks = 13;
    private $SizeOfGFG = 3;
}

// Using ReflectionProperty 
$A = new ReflectionProperty('Company', 'SizeOfGeeksforGeeks');
$B = new ReflectionProperty('Company', 'SizeOfGFG');

// Calling the __toString() function
$C = $A->__toString();
$D = $B->__toString();

// Getting the string form of the specified property.
var_dump($C);
var_dump($D);
?>
```

**输出：**
```
string(52) "Property [ <default> private $SizeOfGeeksforGeeks ]
"
string(42) "Property [ <default> private $SizeOfGFG ]
"
```

### 程序 2
```php
<?php

// Initializing some user-defined classes
class Department1
{
    protected $SizeOfHR;
}
class Department2
{
    public $SizeOfCoding = 6;
}
class Department3
{
    static $SizeOfMarketing = 9;
}

// Using ReflectionProperty over above classes
$A = new ReflectionProperty('Department1', 'SizeOfHR');
$B = new ReflectionProperty('Department2', 'SizeOfCoding');
$C = new ReflectionProperty('Department3', 'SizeOfMarketing');

// Calling the __toString() function and
// getting the string form of the specified property.
var_dump($A->__toString());
var_dump($B->__toString());
var_dump($C->__toString());
?>
```

**输出：**
```
string(43) "Property [ <default> protected $SizeOfHR ]
"
string(44) "Property [ <default> public $SizeOfCoding ]
"
string(44) "Property [ public static $SizeOfMarketing ]
"
```

## 引用
[https://www.php.net/manual/en/reflectionproperty.tostring.php](https://www.php.net/manual/en/reflectionproperty.tostring.php)