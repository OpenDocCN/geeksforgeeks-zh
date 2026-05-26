# PHP 中静态和实例方法的比较

> 原文: [https://www.geeksforgeeks.org/comparison-between-static-and-instance-method-in-php/](https://www.geeksforgeeks.org/comparison-between-static-and-instance-method-in-php/)

## Static methods

PHP 中的静态方法与其他面向对象语言中的静态方法相同。当特定数据在整个类中保持不变时，才应使用静态方法。例如，假设某个程序员正在制作一个学院的数据，其中每个对象都需要一个 `getCollegeName` 函数，该函数为所有对象返回相同的学院名称，那么这个函数就应该被设为静态的。基本上，当需要在没有该类对象的情况下访问该方法时，就会使用静态方法。当有机会在没有类对象帮助的情况下使用方法时，就会使用静态方法。

**示例:**

```php
<?php

// PHP code for static method 
class College
{
    // Static function
    static function getCollegeName()
    {
            return "MNNIT Allahabad";
    }
}

// Calling function without its object
echo (College::getCollegeName());
?>
```

**Output:**

```php
MNNIT Allahabad
```

## Instance Methods

当方法必须在对象存在的情况下才能被调用时，就会使用实例方法。例如，考虑一个 `College` 类，其中有一个 `getPersonName()` 方法，该方法返回人的姓名。这个方法应该只在存在特定类型的人对象时才存在。

**示例:**

```php
<?php
// Program for instance methods

class College
{
    // This data can not be accessed
    // from outside of the class
    private $name;

    // This function sets the name
    function setName($name) {
        $this -> name = $name;
    }

    // This function return name
    function getName() {
        return $this -> name;
    }
}

// Creating an object of type College
$obj = new College;

// Setting name
$obj -> setName("Geeks");

// Getting name
echo ($obj -> getName());
?>
```

**Output:**

```php
Geeks
```

## 实例和静态方法的比较

*   静态方法可以在没有对象的情况下调用，而实例方法不能在没有对象的情况下调用。
*   实例方法的执行时间比静态方法快，但是在 PHP 5.3 版中有一个错误，它说静态方法更快，因为它们引入了后期绑定。

**示例:**

```php
<?php

// Program to compare execution time 
// of static and instance methods
set_time_limit(0);

// Checking php version
echo 'Current PHP version: ' . phpversion();

// Creating class for static
Class St {

    public static $count = 0;

    // function that will print nothing
    public static function getResult()
    {
        self::$count = self::$count + 1;
    }
}

// For calculating time
$time_start_static = microtime(true);

// This loop will run 100000 times
for($i = 0; $i < 100000; $i++) {
    St::getResult();
}

// Execution time for static method ends here
$time_end_static = microtime(true);

// Execution time is end -start time
$time_static = $time_end_static - $time_start_static;

// Printing the result
echo "\nTotal execution time is for static method is: '$time_static'";

// Demo class for instance method
class Ins {
    private $count = 0;

    // Function that will not print anything
    public function getResult() {
        $this -> count = $this -> count + 2;
    }
}

// Creating an instance object
$ob = new Ins;

// Starting time is insitialize
$time_start_instance = microtime(true);

// For time loop is run
for($i = 0; $i < 100000; $i++)
{
    $ob -> getResult();
}

// Execution end for instance method
$time_end_instance = microtime(true);

// Total time is end-start time
$time_instance = $time_end_instance - $time_start_instance;

// Result is printed
echo "\nTotal execution time for instance method is: '$time_instance'";
?>
```

**Output:**

```php
Current PHP version: 7.0.32-0ubuntu0.16.04.1
Total execution time is for static method is: '0.0056149959564209'
Total execution time for instance method is: '0.004885196685791'
```