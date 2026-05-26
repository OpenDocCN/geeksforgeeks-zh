# `assertDirectoryNotExists()`

> Original: [https://www.geeksforgeeks.org/phpunit-assertdirectorynotexists-function/](https://www.geeksforgeeks.org/phpunit-assertdirectorynotexists-function/)

## 描述

`assertDirectoryNotExists()` 函数是 PHPUnit 中的内置函数，用于断言目录路径不存在。 如果给定的目录路径不存在，则此断言将返回 `TRUE`，否则将返回 `FALSE`。 如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertDirectoryNotExists( integer $directory, string $message = '' )
```

## 参数

此函数接受两个参数，如上面的语法所示。 参数描述如下：

*   `$DIRECTORY`: 此参数是一个表示目录路径的字符串。
*   `$Message`: 此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

## 示例程序

以下程序说明了 PHPUnit 中的 `assertDirectoryNotExists()` 函数：

### 程序 1

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertDirectoryNotExists()
    {
        $directoryPath = "/home/shivam/Documents/geeks";

        // Assert function to test whether given
        // directory path exists or not
        $this->assertDirectoryNotExists(
            $directoryPath,
            "directoryPath exists"
        );
    }
}

?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php
use PHPUnit\Framework\TestCase;

class GeeksPhpunitTestCase extends TestCase
{
    public function testPositiveTestcaseForAssertDirectoryNotExists()
    {
        $directoryPath = "/home/shivam/Documents/geeksDoesNotExist/";

        // Assert function to test whether given
        // directory path exists or not
        $this->assertDirectoryNotExists(
            $directoryPath,
            "directoryPath exists"
        );
    }
}

?>
```

发帖主题：Re：Колибри0.7.8.0

## 注意

要使用 `phpunit` 运行测试用例，请执行此处[中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。 此外，`phpunit` 7 及更高版本支持 `assertDirectoryNotExists()`。