# PHPunit assertEquals()函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertequals-function/](https://www.geeksforgeeks.org/phpunit-assertequals-function/)

`assertEquals()`函数是 PHPUnit 中的内置函数，用于断言实际获得的值是否等于期望值。 如果期望值与实际值相同，则此断言将返回 `TRUE`，否则返回 `FALSE`。 如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertEquals( mixed $expected, mixed $actual, string $message = '' )
```

## 参数

此函数接受三个参数，如上面的语法所示。 参数描述如下：

*   `$Expect`: 此参数可以是任何类型，表示期望的数据。
*   `$Actual`: 此参数可以是任何类型，表示实际的数据。
*   `$message`: 此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

## 示例程序

以下程序说明了 PHPUnit 中的 `assertEquals()`函数：

### 程序 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertEquals()
    {
        $expected = "geeks";
        $actual = "Geeks";

        // Assert function to test whether expected
        // value is equal to actual or not
        $this->assertEquals(
            $expected,
            $actual,
            "actual value is not equals to expected"
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
    public function testPositiveTestcaseForAssertEquals()
    {
        $expected = "geeks";
        $actual = "geeks";

        // Assert function to test whether expected
        // value is equal to actual or not
        $this->assertEquals(
            $expected,
            $actual,
            "actual value is not equals to expected"
        );
    }
}
?>
```

## 注意

要使用 `phpunit` 运行测试用例，请执行[此处中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。 此外，`phpunit` 7 及更高版本也支持 `assertEquals()`。