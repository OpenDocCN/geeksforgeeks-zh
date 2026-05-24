# 文件路径。防抱死制动系统()在戈朗的功能举例

> 原文:[https://www . geesforgeks . org/file path-ABS-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-abs-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。Go 语言中的 Abs()** 函数，用于返回指定路径的绝对表示。如果路径不是绝对路径，它将与当前工作目录结合，使其成为绝对路径。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

**语法:**

```go
func Abs(path string) (string, error)

```

这里，“路径”是指定的路径。

**返回值:**返回指定路径的绝对表示。

**例 1:**

```go
// Golang program to illustrate the usage of
// filepath.Abs() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Abs() function to get
    // absolute representation of the specified path
    fmt.Println(filepath.Abs("/home/gfg"))
    fmt.Println(filepath.Abs(".gfg"))
    fmt.Println(filepath.Abs("/gfg"))
    fmt.Println(filepath.Abs(":gfg"))
}
```

**输出:**

```go
/home/gfg <nil>
/.gfg <nil>
/gfg <nil>
/:gfg <nil>

```

**例 2:**

```go
// Golang program to illustrate the usage of
// filepath.Abs() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Abs() function to get
    // absolute representation of the specified path
    fmt.Println(filepath.Abs("/"))
    fmt.Println(filepath.Abs("."))
    fmt.Println(filepath.Abs(":"))
    fmt.Println(filepath.Abs("/."))
    fmt.Println(filepath.Abs("//"))
    fmt.Println(filepath.Abs(":/"))
}
```

**输出:**

```go
/ <nil>
/ <nil>
/: <nil>
/ <nil>
/ <nil>
/: <nil>

```