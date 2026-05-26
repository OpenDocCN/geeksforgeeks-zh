# PHP | 检查变量是否是函数

> 原文: [https://www.geeksforgeeks.org/php-check-if-a-variable-is-a-function/](https://www.geeksforgeeks.org/php-check-if-a-variable-is-a-function/)

为了确定传递的参数是否是函数，下面显示了几个最优选的方法。

## 使用 `is_callable()` 函数

`is_callable()` 是 PHP 的内置函数，用于验证变量的内容是否可以作为函数调用。它可以检查一个简单变量是否包含有效函数的名称，或者一个数组是否包含正确编码的对象和方法名称。

**语法:**

```php
bool is_callable ( $var_name , $syntx_only , $calbl_name )
```

**参数:** `is_callable()` 函数接受三个参数，如上面的语法所示，描述如下。这取决于用户使用多少参数：一、二或三。

*   **`$var_name`**: 存储在字符串变量 `$var_name` 中的函数的名称，或者对象和对象内的方法的名称。
*   **`$syntx_only`**: 如果设置为真，函数只验证名称可能是函数或方法。它将拒绝不是字符串的简单变量，或者没有有效结构用作回调的数组。有效的条目应该只有两个，第一个是对象或字符串，第二个是字符串。
*   **`$calbl_name`**: 它接收可调用的名称。此选项仅针对类实现。

**返回值:** 该函数返回一个布尔类型的值。如果 `$var_name` 是可调用的，则返回真，否则返回假。

**示例:** 本示例使用 `is_callable()` 函数验证参数是否为函数。

```php
<?php

// Declare a variable and initialize
// with function
$function = function() { 
    echo 'GeeksForGeeks'; 
};

// Check is_callable function contains
// function or not
if( is_callable( $function ) ) {
    echo "It is function";
}
else {
    echo "It is not function";
}

// Declare a variable and 
// initialize it
$var = "GeeksForGeeks";
echo "\n";

// Check is_callable function contains
// function or not
if( is_callable( $var ) ) {
    echo "It is function";
}
else {
    echo "It is not function";
}

?>
```

**输出:**

```php
It is function
It is not function
```

## 使用 `instanceof` 运算符

`instanceof` 运算符在 PHP 中用于查明一个对象是否是某个类的实例化对象。

**语法:**

```php
$f instanceof Class_Name
```

**操作数:** 它包含两个操作数，如下所示:

*   **`$f`**: 用作宾语。
*   **`Class_Name`**: 用于保存类名。

**返回值:** 如果对象属于这个类或者这个类是它的父类，它将返回真，否则它将返回假。

**示例:** 这个示例使用 `instanceof` 运算符来确定一个变量是否是 PHP 中的函数。

```php
<?php

// Declare a variable and initialize
// with function
$func = function() { 
    echo 'GeeksforGeeks'; 
};

// Use instanceof to check it contains
// function or not
if($func instanceof Closure) {
    echo "function";
}
else {
    echo "not a function";
}

// Declare a variable and initialize it
$var = "GFG";
echo "\n";

// Use instanceof to check it contains
// function or not
if($var instanceof Closure) {
    echo "function";
}
else{
    echo "not a function";
}
?>
```

**输出:**

```php
function
not a function
```

## 使用 `function_exists()` 方法

**示例:** 本示例使用 `function_exists()` 方法检查参数是否为函数。

```php
<?php

// Declare a function
function myFun() { 
    echo 'GeeksforGeeks'; 
};

// Determine if a variable is a function
function is_function($func) {
    return (is_string($func) && function_exists($func)) 
    || (is_object($func) && ($func instanceof Closure));
}

echo is_function('myFun');

?>
```

**输出:**

```php
1
```