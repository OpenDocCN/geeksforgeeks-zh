# assertNotEmpty() 函数

> 原文：[https://www.geeksforgeeks.org/phpunit-assertnotempty-function/](https://www.geeksforgeeks.org/phpunit-assertnotempty-function/)

`assertNotEmpty()` 函数是 PHPUnit 中的内置函数，用于断言指定的数据持有者是否是非空的。如果提供的数据持有者非空，则此断言将返回 `TRUE`，否则返回 `FALSE`。如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertNotEmpty( mixed $dataHolder, string $message = '' )
```

## 参数

此函数接受两个参数，如上面的语法所示。参数描述如下：

*   `$dataHolder`：此参数可以是任何类型，表示要断言的数据持有者。
*   `$message`：此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

## 示例

以下程序说明了 PHPUnit 中的 `assertNotEmpty()` 函数：

### 程序 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertNotEmpty()
    {
        $dataHolder = '';

        // Assert function to test whether given
        // data holder (variable) is non-empty or not
        $this->assertNotEmpty(
            $dataHolder,
            "data holder is empty"
        );
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
    public function testPositiveTestcaseForAssertNotEmpty()
    {
        $dataHolder = 'test data';

        // Assert function to test whether given
        // data holder (variable) is non-empty or not
        $this->assertNotEmpty(
            $dataHolder,
            "data holder is empty"
        );
    }
}
?>
```

**注意：** 要使用 `phpunit` 运行测试用例，请执行[此处中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。此外，`phpunit` 7 及更高版本也支持 `assertNotEmpty()`。