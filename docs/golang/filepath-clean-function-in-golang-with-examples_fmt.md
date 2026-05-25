# Golang 中的 filepath.Clean() 函数示例

> 原文: [https://www.geeksforgeeks.org/filepath-clean-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-clean-function-in-golang-with-examples/)

在 Go 语言中，`path/filepath` 包用于处理由正斜杠分隔的路径，如 URL 中的路径。`filepath.Clean()` 函数用于通过纯词法处理返回等价于指定路径的最短路径名。该函数在 `path/filepath` 包下定义，使用前需要导入此包。

## 工作原理

此函数反复应用以下规则，直到无法进行进一步处理：

*   用一个分隔符替换多个连续的分隔符元素。
*   如果指定的路径是空字符串，它将返回字符串 `.`。
*   它消除每一个 `.` 路径名元素（当前目录）。
*   它消除每一个非开头的 `..` 路径名元素（父目录）以及其前面的一个非 `..` 元素。
*   它消除开头的 `..` 元素：即如果路径以 `/` 开头，则替换 `/..` 为 `/`（假设分隔符为 `/`）。

## 语法

```go
func Clean(path string) string
```

这里，`path` 是指定的路径。

## 返回值

通过纯词法处理返回与指定路径等价的最短路径名。

## 示例 1

```go
// Golang program to illustrate the usage of
// filepath.Clean() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Clean() function
    fmt.Println(filepath.Clean("/GFG/./../Geeks"))
    fmt.Println(filepath.Clean("GFG/../Geeks"))
    fmt.Println(filepath.Clean("..GFG/./../Geeks"))
    fmt.Println(filepath.Clean("gfg/../../../Geek/GFG"))
}
```

**输出:**

```go
/Geeks
Geeks
Geeks
../../Geek/GFG
```

## 示例 2

```go
// Golang program to illustrate the usage of
// filepath.Clean() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Clean() function
    fmt.Println(filepath.Clean(""))
    fmt.Println(filepath.Clean("."))
    fmt.Println(filepath.Clean("///"))
    fmt.Println(filepath.Clean("/.//"))
    fmt.Println(filepath.Clean("/./"))
    fmt.Println(filepath.Clean(":/"))
}
```

**输出:**

```go
.
.
/
/
/
:
```