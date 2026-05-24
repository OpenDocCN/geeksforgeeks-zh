# 文件路径。Golang 中的 Join()函数示例

> 原文:[https://www . geesforgeks . org/file path-join-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-join-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。Go 语言中的 Join()** 函数，用于将任意数量的指定路径元素连接到单个路径中，必要时添加一个分隔符。该函数对结果调用 Clean，所有空字符串都被忽略。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

**语法:**

```go
func Join(elem ...string) string

```

这里，“elem”是指定的路径元素。

**返回值:**返回连接的单一路径。

**例 1:**

```go
// Golang program to illustrate the usage of
// filepath.Join() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Join() function
    fmt.Println(filepath.Join("G", "F", "G"))
    fmt.Println(filepath.Join("G/F", "G"))
    fmt.Println(filepath.Join("gfg", "GFG"))
    fmt.Println(filepath.Join("Geeks", "for", "Geeks"))
}
```

**输出:**

```go
G/F/G
G/F/G
gfg/GFG
Geeks/for/Geeks

```

**例 2:**

```go
// Golang program to illustrate the usage of
// filepath.Join() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Join() function
    fmt.Println(filepath.Join("/", "/"))
    fmt.Println(filepath.Join(""))
    fmt.Println(filepath.Join("a/b", "/c"))
    fmt.Println(filepath.Join("5", "10"))
    fmt.Println(filepath.Join("."))

}
```

**输出:**

```go
/

a/b/c
5/10
.

```