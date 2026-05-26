# PHPUnit assertLessThanOrEqual() 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertlessthanorequal-function/](https://www.geeksforgeeks.org/phpunit-assertlessthanorequal-function/)

`assertLessThanOrEqual()` 函数是 PHPUnit 中的内置函数，用于断言实际获得的值是否小于或等于期望值。如果实际值小于或等于预期值，则此断言将返回 `TRUE`，否则将返回 `FALSE`。如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertLessThanOrEqual(mixed $expected, mixed $actual [, string $message = ''])
```

## 参数

此函数接受三个参数，如下所述：

*   `$expected`: 此参数可以是任何类型的数值，代表预期的数据。
*   `$actual`: 此参数可以是任何类型的数值，代表实际的数据。
*   `$message`: 此参数接受字符串值。当测试用例失败时，此字符串消息将显示为错误消息。

## 示例

下面的示例说明了 PHPUnit 中的 `assertLessThanOrEqual()` 函数：

### 示例 1

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testNegativeForassertLessThanOrEqualWithEqualVal()
    {    
        $expected = 22; 
        $actual = 420;
        // Assert function to test whether expected 
        // value is less than actual or not 
        $this->assertLessThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is Less than or equal to expected"
        );
    }

    public function testNegativeForassertLessThanOrEqualWithLessVal()
    {  
        $expected = 22; 
        $actual = 220;
        // Assert function to test whether expected 
        // value is less than actual or not
        $this->assertLessThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is Less than or equal to expected"
        ); 
    }  
} 
?>
```

### 示例 2

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testPositiveForassertLessThanOrEqualWithEqualVal()
    {    
        $expected = 22; 
        $actual = 10;
        // Assert function to test whether expected 
        // value is less than actual or not 
        $this->assertLessThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is greater than or equal to expected"
        );
    }

    public function testPositiveForassertLessThanOrEqualWithLessVal()
    {  
        $expected = 22; 
        $actual = 22;
        // Assert function to test whether expected 
        // value is less than actual or not
        $this->assertLessThanOrEqual( 
            $expected, 
            $actual, 
            "actual value is greater than or equal to expected"
        ); 
    }  
} 
?>
```

**引用：** [https://phpunit.readthedocs.io/en/9.2/assertions.html#assertlessthanorequal](https://phpunit.readthedocs.io/en/9.2/assertions.html#assertlessthanorequal)