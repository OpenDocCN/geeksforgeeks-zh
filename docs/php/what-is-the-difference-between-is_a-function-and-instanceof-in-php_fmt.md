# PHP 中 `is_a()` 函数和 `instanceof` 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-is_a-function-and-instanceof-in-php/](https://www.geeksforgeeks.org/what-is-the-difference-between-is_a-function-and-instanceof-in-php/)

## `is_a()` 函数

`is_a()` 是 PHP 的内置函数，用于检查给定对象是否属于给定类。它还会检查给定类是否是该对象的父类之一。

**语法：**

```php
bool is_a( $object, $class_name, $allow_string )
```

**参数：** 该函数接受三个参数，描述如下：

*   `对象`：此参数用于容纳被测对象。
*   `类名`：此参数用于保存类名。
*   `allow_string`： 如果该参数设置为 `False`，则不允许字符串类名作为对象。

**返回值：** 如果对象属于这个类或者这个类是它的父类，这个函数返回 `true`，否则它将返回 `false`。

下面的程序说明 `is_a()` 函数：

```php
<?php 
// PHP program to illustrate the  
// is_a() function

// sample class 
class GeeksforGeeks { 
    var $store = 'Hello geeks!'; 
}

// create a new object 
$geek = new GeeksforGeeks();

// checks if $geek is an object 
// of class GeeksforGeeks 
if (is_a($geek, 'GeeksforGeeks')) { 
    echo "Yes"; 
}

?>
```

**输出：**

```php
Yes
```

## `instanceof` 运算符

`instanceof` 运算符用于在 PHP 中查明一个对象是否是某个类的实例化对象。

**语法：**

```php
$a instanceof MyClass
```

**操作数：** 该运算符包含两个操作数：

*   `$a`： 这个用作对象。
*   `MyClass`： 是类名。

**返回值：** 如果对象属于这个类或者这个类是它的父类，它将返回 `true`，否则它将返回 `false`。

下面的程序说明了 PHP 中的 `instanceof` 运算符：

```php
<?php
// PHP program to illustrate instanceof
// operator

// sample class 
class GeeksforGeeks { 
    var $store = 'Hello geeks!'; 
}

// create a new object 
$geek = new GeeksforGeeks();

// Checks if $geek is an object of 
// class GeeksforGeeks 
if ($geek instanceof GeeksforGeeks) {
    echo "Yes";
}

?>
```

**输出：**

```php
Yes
```

## `is_a()` 函数和 `instanceof` 运算符的区别

*   `is_a()` 是一个函数，而 `instanceof` 是一个语言构造。`is_a()` 函数将明显慢一些，因为它有执行函数调用的所有开销。
*   如果函数中的回调（如 `array_map`）需要使用，`instanceof` 不是函数，它是一个语言构造，因此不能用作回调。另一方面，回调可以使用 `is_a()` 函数。
*   `instanceof` 使用的直接类名比 `is_a()` 函数短。
    **例：**

```php
    // Short syntax (comparatively)
    $a instanceof MyClass

    is_a( $a, MyClass::class )
```

*   `is_a()` 作为函数，第一个参数接受一个对象，第二个参数接受一个字符串，而 `instanceof` 第一个参数接受一个对象，第二个参数可以接受类名、对象实例或类标识符（不带引号的类名）。

**`is_a()` 示例：**

```php
    // Only way to call it
    is_a( $object, $string );
```

**`instanceof` 示例：**

```php
    // Object instance      
    $object instanceof $otherObject;

    // String class name
    $object instanceof $string;

    // Identifier for the class
    $object instanceof ClassName;
```