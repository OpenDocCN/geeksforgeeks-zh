# PHPUnit assertNotContainsOnly()函数

## 概述

`assertNotContainsOnly()`函数是 PHPUnit 中的一个内置函数，用于断言一个数组不包含作为给定数据类型的所有值。 如果数组包含给定数据类型以外的值，则此断言将返回 `TRUE`，否则返回 `FALSE`。 如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertNotContainsOnly( string $dataType, array $array,
                 boolean $isNativeType = null, string $message = '' )
```

## 参数

此函数接受四个参数，如上面的语法所示。 参数说明如下：

*   `$dataType`: 此参数是一个由数据类型名称组成的字符串。
*   `$array`: 此参数是一个数组，`assertNotContainsOnly`函数将检查它是否仅包含给定类型的值。
*   `$isNativeType`: 此参数指示数据类型是否为 PHP 原生数据类型。
*   `$message`: 此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

以下程序说明了 PHPUnit 中的 `assertNotContainsOnly()`函数：

## 示例程序

### 程序1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertNotContainsOnly()
    {
        $testArray = array("geeksforgeek", "true");
        $dataType = "string";

        // Assert function to test whether testArray contains
        // only string values or not
        $this->assertNotContainsOnly($dataType, $testArray, null,
                 "testArray contains only string") ;
    }
}
?>
```

### 程序2

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testPositiveTestcaseForAssertNotContainsOnly()
    {
        $testArray = array("geeksforgeek", 4);
        $dataType = "string";

        // Assert function to test whether testArray contains
        // only string values
        $this->assertNotContainsOnly($dataType, $testArray, null,
               "testArray  contains only string") ;
    }
}
?>
```

## 注意

要使用 `phpunit` 运行测试用例，请执行[此处中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。 此外，`phpunit` 7 及更高版本支持 `assertNotContainsOnly()`。