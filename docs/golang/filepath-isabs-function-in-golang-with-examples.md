# 文件路径。Golang 中的 IsAbs()函数示例

> 原文:[https://www . geesforgeks . org/file path-isabs-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-isabs-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。Go 语言中的 IsAbs()** 函数，用于报告路径是否为绝对路径。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

**语法:**

```go
func IsAbs(path string) bool

```

这里，“路径”是指定的绝对路径或非绝对路径。

**返回值:**对于绝对路径返回真，否则返回假。

**例 1:**

```go
// Golang program to illustrate the usage of
// filepath.IsAbs() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the IsAbs() function with
    // some absolute and unabsolute paths
    fmt.Println(filepath.IsAbs("/home/gfg"))
    fmt.Println(filepath.IsAbs(".gfg"))
    fmt.Println(filepath.IsAbs("/gfg"))
    fmt.Println(filepath.IsAbs(":gfg"))
}
```

**输出:**

```go
true
false
true
false

```

**例 2:**

```go
// Golang program to illustrate the usage of
// filepath.IsAbs() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the IsAbs() function with
    // some absolute and unabsolute paths
    fmt.Println(filepath.IsAbs("/"))
    fmt.Println(filepath.IsAbs("."))
    fmt.Println(filepath.IsAbs(":"))
    fmt.Println(filepath.IsAbs("/."))
    fmt.Println(filepath.IsAbs("//"))
    fmt.Println(filepath.IsAbs(":/"))
}
```

**输出:**

```go
true
false
false
true
true
false

```