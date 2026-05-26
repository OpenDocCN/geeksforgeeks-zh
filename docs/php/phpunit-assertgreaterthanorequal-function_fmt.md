# PHPUnit `assertGreaterThanOrEqual()` 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertgreaterthanorequal-function/](https://www.geeksforgeeks.org/phpunit-assertgreaterthanorequal-function/)

`assertGreaterThanOrEquity()` 函数是 PHPUnit 中的内置函数，用于断言实际获得的值是否大于或等于期望值。如果实际值大于或等于预期值，则此断言将返回 `TRUE`，否则将返回 `FALSE`。如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertGreaterThanOrEqual(mixed $expected, mixed $actual [, string $message = ''])
```

## 参数

此函数接受三个参数，如下所述：

*   `$Expect`: 此参数可以是任何类型的数值，表示预期的数据。
*   `$Actual`: 此参数可以是任何类型的数值，表示实际的数据。
*   `$message`: 此参数接受字符串值。当测试用例失败时，此字符串消息将显示为错误消息。

下面的示例说明了 PHPUnit 中的 `assertGreaterThanOrEquity()` 函数：

### 示例 1

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testNegativeForassertGreaterThanOrEqualWithEqualVal()
    {    
        $expected = 22; 
        $actual = 10;
        // Assert function to test whether actual 
        // value is greater than or equal to expected or not 
        $this->assertGreaterThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is greater than or equal to expected"
        );
    }

    public function testNegativeForassertGreaterThanOrEqualWithGreaterVal()
    {  
        $expected = 22; 
        $actual = 10;
        // Assert function to test whether actual
        // value is greater than or equal to expected or not
        $this->assertGreaterThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is greater than or equal to expected"
        ); 
    }  
} 
?>
```

发帖主题：Re：Колибри0.7.8.0

### 示例 2

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testPositiveForassertGreaterThanOrEqualWithEqualVal()
    {    
        $expected = 11; 
        $actual = 11;
        // Assert function to test whether actual
        // value is greater than or equal to expected or not 
        $this->assertGreaterThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is greater than or equal to expected"
        );
    }

    public function testPositiveForassertGreaterThanOrEqualWithGreaterVal()
    {  
        $expected = 11; 
        $actual = 12;
        // Assert function to test whether actual
        // value is greater than or equal to expected or not
        $this->assertGreaterThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is greater than or equal to expected"
        ); 
    }  
} 
?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：** [https://phpunit.readthedocs.io/en/9.2/assertions.html#assertgreaterthanorequal](https://phpunit.readthedocs.io/en/9.2/assertions.html#assertgreaterthanorequal)