# 文件路径。Golang 中 Ext()函数示例

> 原文:[https://www . geesforgeks . org/file path-ext-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-ext-function-in-golang-with-examples/)

在 Go 语言中，*路径*包用于由转发斜线分隔的路径，如 URL 中的路径。**文件路径。Go 语言中的 Ext()** 函数，用于返回指定路径使用的文件扩展名。扩展名是从 path 最后一个元素的最后一个点开始的后缀；如果没有点，它是空的。此外，该函数是在路径包下定义的。在这里，您需要导入“path/filepath”包才能使用这些功能。

**语法:**

```go
func Ext(path string) string

```

这里，“路径”是指定的路径。

**返回值:**返回指定路径使用的文件扩展名。

**例 1:**

```go
// Golang program to illustrate the usage of
// filepath.Ext() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Ext() function
    fmt.Println(filepath.Ext("gfg.org"))
    fmt.Println(filepath.Ext("GeeksforGeeks."))
    fmt.Println(filepath.Ext(".org"))

}
```

**输出:**

```go
.org
.
.org

```

**例 2:**

```go
// Golang program to illustrate the usage of
// filepath.Ext() function

// Including the main package
package main

// Importing fmt and path/filepath
import (
    "fmt"
    "path/filepath"
)

// Calling main
func main() {

    // Calling the Ext() function
    fmt.Println(filepath.Ext("a.b"))
    fmt.Println(filepath.Ext("gfg"))
    fmt.Println(filepath.Ext("ide.gfg.org"))
    fmt.Println(filepath.Ext(".ab.cd"))

}
```

**输出:**

```go
.b

.org
.cd

```