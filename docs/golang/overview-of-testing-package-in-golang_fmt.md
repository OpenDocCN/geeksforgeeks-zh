# Go语言测试包概述

> 原文: [https://www.geeksforgeeks.org/overview-of-testing-package-in-golang/](https://www.geeksforgeeks.org/overview-of-testing-package-in-golang/)

在软件行业，手动测试和自动测试之间有明显的区别。其中手动测试用于确保软件代码按预期运行，并且需要时间和精力。大多数手动测试包括检查日志文件、外部服务和数据库中的错误。以不同的方式，自动化测试也是自动化的，某些软件/代码像用户一样执行测试。因为自动化测试是使用自动化工具完成的，所以探索测试花费更少的时间和更多的测试脚本，同时增加了测试的整体范围。

在Golang中，`testing`包负责不同类型的测试，可能是性能测试、并行测试、功能测试，或者所有这些测试的任何可能组合。

`testing`包提供了对Golang代码自动化测试的支持。要运行任何测试功能，请使用`go test`命令，该命令自动执行任何形如`func TestXxx(*testing.T)`的函数，其中`Xxx`不得以任何小写字母开头。

**测试函数语法:**

```go
func TestXxx(*testing.T)
```

**在Golang编写测试套件的步骤:**

*   创建一个文件名以`_test.go`结尾的文件
*   通过导入`"testing"`命令导入包测试
*   编写形如`func TestXxx(t *testing.T)`的测试函数，使用`Error`、`Errorf`、`Fail`或相关方法中的任何一种来发出故障信号。
*   将文件放入任何包中。
*   运行`go test`命令

**注意:** 测试文件将被排除在包构建之外，仅将在`go test`命令上执行。

**例:**

*文件:*

## Go

```go
package main

// function which return "geeks"
func ReturnGeeks() string{
    return "geeks";
}

// main function of package
func main() {
    ReturnGeeks()
}
```

*测试文件: `pkg_Test.go`*

## Go

```go
package main

import (
    "testing"
)

// test function
func TestReturnGeeks(t *testing.T) {
    actualString := ReturnGeeks()
    expectedString := "geeks"
    if actualString != expectedString{
        t.Errorf("Expected String(%s) is not same as"+
         " actual string (%s)", expectedString,actualString)
    }
}
```

**输出:**

[![](img/be9d12927698ef26f6b8ca91ae045d27.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200714154610/golangtestscreenshot.png)

运行测试用例后的屏幕