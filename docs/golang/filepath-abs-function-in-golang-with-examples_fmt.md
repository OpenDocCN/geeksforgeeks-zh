# filepath.Abs()函数在Go语言中的功能举例

> 原文: [https://www.geeksforgeeks.org/filepath-abs-function-in-golang-with-examples/](https://www.geeksforgeeks.org/filepath-abs-function-in-golang-with-examples/)

在 Go 语言中，`path/filepath`包用于处理由正斜杠分隔的路径，如 URL 中的路径。`filepath.Abs()`函数用于返回指定路径的绝对表示。如果路径不是绝对路径，它将与当前工作目录结合，使其成为绝对路径。此外，该函数是在`path/filepath`包下定义的。在这里，您需要导入`"path/filepath"`包才能使用这些功能。

## 语法:

```go
func Abs(path string) (string, error)
```

这里，`path`是指定的路径。

**返回值:** 返回指定路径的绝对表示。

## 例 1:

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

### 输出:

```go
/home/gfg <nil>
/.gfg <nil>
/gfg <nil>
/:gfg <nil>
```

## 例 2:

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

### 输出:

```go
/ <nil>
/ <nil>
/: <nil>
/ <nil>
/ <nil>
/: <nil>
```