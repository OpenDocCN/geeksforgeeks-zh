# assertDirectoryNotIsWritable() 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertdirectorynotiswritable-function/](https://www.geeksforgeeks.org/phpunit-assertdirectorynotiswritable-function/)

`assertDirectoryNotIsWritable()` 函数是 PHPUnit 中的内置函数，用于断言指定的目录不是目录还是不可写。 如果给定的目录路径不存在或不可写，则此断言将返回 `TRUE`，否则将返回 `FALSE`。 如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertDirectoryNotIsWritable( integer $directory, string $message = '' )
```

## 参数

此函数接受两个参数，如上面的语法所示。 参数描述如下：

*   `$directory`: 此参数是一个表示目录路径的字符串。
*   `$message`: 此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

## 示例

以下程序说明了 PHPUnit 中的 `assertDirectoryNotIsWritable()` 函数：

### 程序 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForassertDirectoryNotIsWritable()
    {
        $directoryPath = "/home/shivam/Documents/phpunit/notwritable";

        // Assert function to test whether given
        // directory path either doesn't exists or not writable
        $this->assertDirectoryNotIsWritable(
            $directoryPath,
            "directoryPath either doesn't exists or not writable"
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
    public function testPositiveTestcaseForAssertDirectoryNotIsWritable()
    {
        $directoryPath = "/home/shivam/Documents/geeks";

        // Assert function to test whether given
        // directory path exists or not writable
        $this->assertDirectoryNotIsWritable(
            $directoryPath,
            "directoryPath either doesn't exists or not writable"
        );
    }
}

?>
```

## 注意

要使用 `phpunit` 运行测试用例，请执行[此处中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。 此外，`phpunit` 7 及更高版本支持 `assertDirectoryNotIsWritable()`。