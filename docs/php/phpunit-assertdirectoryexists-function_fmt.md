# PHPUnit `assertDirectoryExists()` 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertdirectoryexists-function/](https://www.geeksforgeeks.org/phpunit-assertdirectoryexists-function/)

`assertDirectoryExists()` 函数是 PHPUnit 中的内置函数，用于断言目录路径是否存在。如果给定的目录路径存在，则此断言将返回 `TRUE`，否则将返回 `FALSE`。如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertDirectoryExists( string $directory, string $message = '' )
```

## 参数

此函数接受两个参数，如上面的语法所示。参数描述如下：

*   `$directory`: 此参数是一个字符串，表示目录路径。
*   `$message`: 此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

## 示例

以下程序说明了 PHPUnit 中的 `assertDirectoryExists()` 函数：

### 程序 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertDirectoryExists()
    {
        $directoryPath = "/home/shivam/Documents/geeksDoesNotExist/";

        // Assert function to test whether given
        // directory path exists or not
        $this->assertDirectoryExists(
            $directoryPath,
            "directoryPath doesn't exists"
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
    public function testPositiveTestcaseForAssertDirectoryExists()
    {
        $directoryPath = "/home/shivam/Documents/geeks/";

        // Assert function to test whether given
        // directory path exists or not
        $this->assertDirectoryExists(
            $directoryPath,
            "directoryPath exists"
        );
    }
}
?>
```

**注意：** 要使用 `phpunit` 运行测试用例，请执行[此处中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。此外，`phpunit` 7 及更高版本也支持 `assertDirectoryExists()`。