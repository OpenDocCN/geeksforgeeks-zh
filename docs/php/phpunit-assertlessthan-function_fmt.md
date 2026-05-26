# PHPUnit assertLessThan()函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertlessthan-function/](https://www.geeksforgeeks.org/phpunit-assertlessthan-function/)

`assertLessThan()`函数是 PHPUnit 中的内置函数，用于断言实际获得的值是否小于期望值。 如果实际值小于期望值，则此断言将返回 `TRUE`，否则返回 `FALSE`。 如果为 `true`，则断言的测试用例通过，否则测试用例失败。

**语法：**

```php
assertLessThan(mixed $expected, mixed $actual [, string $message = ''])
```

**参数：**此函数接受三个参数，如上所述，如下所述：

*   `$Expect`: 此参数可以是任何类型的数值，表示期望的数据。
*   `$Actual`: 此参数可以是任何类型的数值，表示实际的数据。
*   `$message`: 此参数接受字符串值。当测试用例失败时，此字符串消息将显示为错误消息。

以下示例说明了 PHPUnit 中的 `assertLessThan()`函数：

### 示例 1

```php
<?php 
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase 
{ 
    public function testNegativeTestcaseForassertLessThan()
    {    
        $expected = 11; 
        $actual = 22;

        // Assert function to test whether expected 
        // value is less than actual or not 
        $this->assertLessThan( 
            $expected, 
            $actual, 
            "actual value is not less than expected"
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
    public function testPositiveTestcaseForassertLessThan()
    {    
        $expected = 22; 
        $actual = 11;

        // Assert function to test whether expected 
        // value is less than actual or not 
        $this->assertLessThan( 
            $expected, 
            $actual, 
            "actual value is not less than expected"
        ); 
    } 
}
?> 
```

发帖主题：Re：Колибри0.7.8.0

**引用：**[https://phpunit.readthedocs.io/en/9.2/assertions.html#assertlessthan](https://phpunit.readthedocs.io/en/9.2/assertions.html#assertlessthan)