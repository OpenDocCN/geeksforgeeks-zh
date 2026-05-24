# 异常::getMessage 和异常::getLine 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-exceptiongetmessage-and-exception-getline/](https://www.geeksforgeeks.org/difference-between-exceptiongetmessage-and-exception-getline/)

## 异常::getMessage

PHP 语言中的 `Exception::getMessage` 异常基本上是程序员用来知道异常消息的。这意味着每当代码中出现异常情况时，为了知道确切的含义以及该异常是关于什么的，就使用了这个函数。这个函数对程序员来说非常有用，因为它帮助他/她找到异常的真正本质，并使用这些有价值的信息编写正确的异常处理代码。

**示例:** 在下面的代码中，`getMessage()` 将获得异常消息。

```php
<?php
    try {
        throw new Exception(" error message");
    } catch(Exception $e) {
        echo $e->getMessage();
    }
?>
```

**Output**

```
 error message
```

## 异常::getLine

PHP 语言中的 `Exception::getLine` 异常基本上是程序员为了知道对应的异常发生在哪一行而使用的。这意味着每当代码中出现异常时，这个特殊的 `getLine()` 函数可以找出发生异常的代码的确切位置。当我们有大量的代码并且无法找到特定异常的位置时，这个功能会有所帮助。

**示例:** 在下面的代码中，`getLine()` 函数将获得发生异常的行。

```php
<?php
    try {
        throw new Exception(" error message");
    } catch(Exception $e) {
        echo "The exception has occured on line: " 
             . $e->getLine();
    }
?>
```

**Output**

```
The exception has occured on line: 3
```

## 异常的区别::getMessage 和 Exception::getLine

| **Exception::getMessage** | **Exception::getLine** |
| :--- | :--- |
| 此函数返回异常消息。 | 此函数返回发生异常的行的位置。 |
| 它以字符串格式返回异常消息。 | 以整数格式返回行号。 |
| 它对所有类型的代码都有帮助。 | 它在大型代码（即包含多行的代码）中最有帮助。 |