# PHPUnit assertIsNumeric() 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertisnumeric-function/](https://www.geeksforgeeks.org/phpunit-assertisnumeric-function/)

`assertIsNumeric()` 函数是 `PHPUnit` 中的内置函数，用于断言给定的实际变量是否为数字。如果实际变量是数值，则此断言将返回 `TRUE`，否则将返回 `FALSE`。如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法：

```php
assertIsNumeric($actual[, $message = ''])
```

## 参数：

此函数接受上述两个参数，如下所述：

*   `$Actual`：此参数可以是任何类型的变量，代表实际数据。
*   `$Message`：此参数接受字符串值。当测试用例失败时，此字符串消息将显示为错误消息。

下面的示例说明了 `PHPUnit` 中的 `assertIsNumeric()` 函数：

### 示例 1：

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testNegativeForassertIsNumeric()
    {   
        $actualvalue = "hello";
        // Assert function to test whether actual 
        // variable is numeric or not
        $this->assertIsNumeric(
            $actualvalue, 
            "actual value is Numeric or not"
        );
    }
} 
?>
```

### 示例 2：

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testPositiveForassertIsNumeric()
    {   
        $actualvalue = "1111";
        // Assert function to test whether actual 
        // variable is numeric or not
        $this->assertIsNumeric(
            $actualvalue, 
            "actual value is Numeric or not"
        );
    }
} 
?>
```

**引用：** [https://phpunit.readthedocs.io/en/9.2/assertions.html#assertisnumeric](https://phpunit.readthedocs.io/en/9.2/assertions.html#assertisnumeric)