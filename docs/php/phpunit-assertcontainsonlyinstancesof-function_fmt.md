# PHPunit `assertContainsOnlyInstancesOf()` 函数

> Original: [https://www.geeksforgeeks.org/phpunit-assertcontainsonlyinstancesof-function/](https://www.geeksforgeeks.org/phpunit-assertcontainsonlyinstancesof-function/)

`assertContainsOnlyInstancesOf()` 函数是 PHPUnit 中的一个内置函数，用于断言一个数组将其所有值作为给定类的实例。 如果数组只包含给定类的实例，则此断言将返回 `TRUE`，否则将返回 `FALSE`。 如果为 `true`，则断言的测试用例通过，否则测试用例失败。

## 语法

```php
assertContainsOnlyInstancesOf( string $classname, array $array, string $message = '' )
```

## 参数

此函数接受三个参数，如上面的语法所示。 参数描述如下：

*   `$className`: 此参数是一个字符串，即类的名称。
*   `$array`: 此参数是一个数组，断言函数检查它是否只包含给定类的实例。
*   `$message`: 此参数接受字符串值。当测试用例失败时，该字符串消息将显示为错误消息。

以下程序说明了 PHPUnit 中的 `assertContainsOnlyInstancesOf()` 函数：

## 程序 1

```php
<?php

use PHPUnit\Framework\TestCase;

class Foo {
    public function dummyFunction(){return true;}
}

class Bar {
    public function dummyFunction(){return true;}
}

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertContainsOnlyInstancesOf()
    {

// Assert function to test whether testArray contains
        // only instance of Foo or not
        $this->assertContainsOnlyInstancesOf(
            Foo::class,
            [new Foo, new Bar, new Foo], 
            "testArray doesn't contains only instance of Foo"
        );
    }
}

?>
```

发帖主题：Re：Колибри0.7.8.0

## 程序 2

```php
<?php
use PHPUnit\Framework\TestCase;

class Foo {
    public function dummyFunction(){return true;}
}

class Bar {
    public function dummyFunction(){return true;}
}

class GeeksPhpunitTestCase extends TestCase
{
    public function testNegativeTestcaseForAssertContainsOnlyInstancesOf()
    {
        // Assert function to test whether testArray contains
        // only instance of Foo or not
        $this->assertContainsOnlyInstancesOf(
            Foo::class,
            [new Foo, new Foo],
            "testArray contains only instance of Foo"
        );
    }
}

?>
```

发帖主题：Re：Колибри0.7.8.0

**注意：** 要使用 `phpunit` 运行测试用例，请执行此处[中的步骤](https://www.jetbrains.com/help/phpstorm/using-phpunit-framework.html)。 此外，`phpunit` 7 及更高版本支持 `assertContainsOnlyInstancesOf()`。