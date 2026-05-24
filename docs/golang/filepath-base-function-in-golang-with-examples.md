# 文件路径。Golang 中的 Base()函数示例

> 原文:[https://www . geesforgeks . org/file path-base-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-base-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。base()**Go 语言中的函数，用于返回指定路径的最后一个元素。在这里，在提取最后一个元素之前，尾部路径分隔符被移除。如果路径为空，Base 将返回“”。如果路径完全由分隔符组成，Base 将返回一个分隔符。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

**语法:**

```go
func Base(path string) string

```

这里，“路径”是指定的路径。

**返回值:**返回指定路径的最后一个元素。如果路径为空，此函数将返回“”。如果路径完全由分隔符组成，此函数返回一个分隔符。

**例 1:**

```go
// Golang program to illustrate the usage of
// filepath.Base() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Base() function to
    // get the last element of path
    fmt.Println(filepath.Base("/home/gfg"))
    fmt.Println(filepath.Base(".gfg"))
    fmt.Println(filepath.Base("/gfg"))
    fmt.Println(filepath.Base(":gfg/GFG"))
}
```

**输出:**

```go
gfg
.gfg
gfg
GFG

```

**例 2:**

```go
// Golang program to illustrate the usage of
// filepath.Base() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Base() function which
    // returns "." if the path is empty
    // and returns a single separator if
    // the path consists entirely of separators
    fmt.Println(filepath.Base(""))
    fmt.Println(filepath.Base("."))
    fmt.Println(filepath.Base("/"))
    fmt.Println(filepath.Base("/."))
    fmt.Println(filepath.Base("//"))
    fmt.Println(filepath.Base(":/"))

}
```

**输出:**

```go
.
.
/
.
/
:

```