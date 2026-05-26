# PHPUnit assertFileIsReadable() 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertfileisreadable-function/](https://www.geeksforgeeks.org/phpunit-assertfileisreadable-function/)

`assertFileIsReadable()` 函数是 PHPUnit 中的一个内置函数，用于断言指定的文件名是否可读。如果给定的文件名存在且可读，则此断言将返回 `TRUE`，否则返回 `FALSE`。如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertFileIsReadable(string $filename[, string $message = ''])
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$filename`: 此参数是一个表示文件名的字符串。
*   `$message`: 此参数接受字符串值。当测试用例失败时，此字符串消息将显示为错误消息。

以下示例说明了 PHPUnit 中的 `assertFileIsReadable()` 函数：

## 示例 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertFileIsReadable()
    {
        $filename = "/home/lovely/Documents/phpunit";

        // Assert function to test whether the given
        // file name either exists and readable
        $this->assertFileIsReadable(
            $filename,
            "File name exists and readable"
        );
    }
}
?>
```

发帖主题：Re：Колибри0.7.8.0

## 示例 2

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testPositiveTestcaseForAssertFileIsReadable()
    {
        $filename = "/home/lovely/Documents/php";

        // Assert function to test whether the given
        // file name either exists and readable
        $this->assertFileIsReadable(
            $filename,
            "File name exists and readable"
        );
    }
}
?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：** [https://phpunit.readthedocs.io/en/9.2/assertions.html#assertfileisreadable](https://phpunit.readthedocs.io/en/9.2/assertions.html#assertfileisreadable)