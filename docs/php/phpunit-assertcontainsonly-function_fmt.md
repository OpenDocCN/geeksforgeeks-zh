# PHPUnit `assertContainsOnly()` 函数

> 原文：[https://www.geeksforgeeks.org/phpunit-assertcontainsonly-function/](https://www.geeksforgeeks.org/phpunit-assertcontainsonly-function/)

`assertContainsOnly()` 函数是 PHPUnit 中的内置函数，用于断言数组将其所有值包含为给定的数据类型。如果数组只包含给定数据类型的值，则此断言将返回 `TRUE`，否则返回 `FALSE`。如果为 `TRUE`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertContainsOnly(string $dataType, array $array,
                 boolean $isNativeType = null, string $message = '')
```

## 参数

此函数接受四个参数，如上面的语法所示。参数说明如下：

*   `$dataType`：此参数是一个字符串，由数据类型名称组成。
*   `$array`：此参数是一个数组，`assertContainsOnly` 函数将检查它是否只包含给定类型的值。
*   `$isNativeType`：此参数指示数据类型是否为 PHP 原生数据类型。
*   `$message`：此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

## 示例程序

以下程序说明了 PHPUnit 中的 `assertContainsOnly()` 函数：

### 程序 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertContainsOnly()
    {
        $testArray = array("geeksforgeek", 2);
        $dataType = "string";
        // assert function to test whether testArray contains
        // only string values
        $this->assertContainsOnly($dataType, $testArray, null,
                 "testArray doesn't  contains only string") ;
    }
}

?>
```

### 程序 2

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testPositiveTestcaseForAssertContainsOnly()
    {
        $testArray = array("geeksforgeek", "learn");
        $dataType = "string";
        // assert function to test whether testArray contains
        // only string values
        $this->assertContainsOnly($dataType, $testArray, null,
               "testArray doesn't  contains only string") ;
    }
}

?>
```

## 注意

要使用 `phpunit` 运行测试用例，请执行[此处](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)的步骤。此外，`phpunit` 7 及更高版本支持 `assertContainsOnly()`。