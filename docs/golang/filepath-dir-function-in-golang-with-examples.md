# 文件路径。Golang 中的 Dir()函数示例

> 原文:[https://www . geesforgeks . org/file path-dir-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-dir-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。Go 语言中的 Dir()** 函数，用于返回指定路径中除最后一个元素以外的所有元素。删除最后一个元素后，Dir 在路径上调用 Clean，并移除尾随斜线。如果路径为空，目录将返回“”。如果路径完全由分隔符组成，Dir 返回一个分隔符。除非是根目录，否则返回的路径不会以分隔符结尾。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

**语法:**

```go
func Dir(path string) string

```

这里，“路径”是指定的路径。

**返回值:**返回指定路径除最后一个元素外的所有元素。

**例 1:**

```go
// Golang program to illustrate the usage of
// filepath.Dir() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Dir() function
    fmt.Println(filepath.Dir("/Geeks/GFG/gfg.org"))
    fmt.Println(filepath.Dir("/Geeks/GFG/gfg"))
    fmt.Println(filepath.Dir("/Geeks/GFG/gfg/"))
    fmt.Println(filepath.Dir("/GFG/gfg///"))
    fmt.Println(filepath.Dir("/gfg.org"))
    fmt.Println(filepath.Dir("gfg.org"))
}
```

**输出:**

```go
/Geeks/GFG
/Geeks/GFG
/Geeks/GFG/gfg
/GFG/gfg
/
.

```

**例 2:**

```go
// Golang program to illustrate the usage of
// filepath.Dir() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Dir() function
    fmt.Println(filepath.Dir(""))
    fmt.Println(filepath.Dir("."))
    fmt.Println(filepath.Dir("/"))
    fmt.Println(filepath.Dir("//"))
    fmt.Println(filepath.Dir("../gfg.org"))

}
```

**输出:**

```go
.
.
/
/
..

```