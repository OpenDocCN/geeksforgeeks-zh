# 文件路径。Golang 中的 Clean()功能示例

> 原文:[https://www . geesforgeks . org/file path-clean-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-clean-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。Go 语言中的 Clean()** 函数，用于通过纯词法处理返回等价于指定路径的最短路径名。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

此功能反复应用以下规则，直到无法进行进一步处理:

*   它用一个分隔符替换多个分隔符元素。
*   如果指定的路径是空字符串，它将返回字符串“”。。
*   它消除了每一个。路径名元素(当前目录)。
*   它消除了每个内在的..路径名元素(父目录)以及非..它前面的元素。
*   它消除了..以根路径开头的元素:即替换“/..”假设分隔符为“/”，路径开头的“/”。

**语法:**

```go
func Clean(path string) string

```

这里，“路径”是指定的路径。

**返回值:**通过纯词法处理返回与指定路径等价的最短路径名。

**例 1:**

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

**例 2:**

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