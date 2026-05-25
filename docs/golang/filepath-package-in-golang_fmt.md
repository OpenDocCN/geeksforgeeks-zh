# Go语言的filepath包

> 原文：[https://www.geeksforgeeks.org/filepath-package-in-golang/](https://www.geeksforgeeks.org/filepath-package-in-golang/)

Go语言为实现实用程序提供了内置支持，这些实用程序在`filepath`包的帮助下以与目标操作系统定义的文件路径兼容的方式操作文件名路径。这个包使用正斜杠或反斜杠（取决于操作系统）来处理路径，例如，总是使用正斜杠的网址。

## 函数列表

| 功能 | 描述 |
| --- | --- |
| [`Abs()`](https://www.geeksforgeeks.org/filepath-abs-function-in-golang-with-examples/) | 此函数用于返回路径的绝对表示。 |
| [`Base()`](https://www.geeksforgeeks.org/filepath-base-function-in-golang-with-examples/) | 该函数用于返回路径的最后一个元素。 |
| [`Clean()`](https://www.geeksforgeeks.org/filepath-clean-function-in-golang-with-examples/) | 该函数用于通过纯词法处理返回与路径等价的最短路径名。 |
| [`Dir()`](https://www.geeksforgeeks.org/filepath-dir-function-in-golang-with-examples/) | 该函数用于返回除最后一个路径元素之外的所有元素，通常是路径的目录。 |
| `EvalSymlinks()` | 此函数用于在评估任何符号链接后返回路径名。 |
| [`Ext()`](https://www.geeksforgeeks.org/filepath-ext-function-in-golang-with-examples/) | 此函数用于返回`path`使用的文件扩展名。 |
| `FromSlash()` | 此函数用于返回用分隔符替换路径中每个斜杠（`/`）字符的结果。 |
| `Glob()` | 该函数用于返回所有匹配模式的文件的名称，如果没有匹配的文件，则返回零。 |
| `Join()` | 该函数用于将任意数量的路径元素连接到单个路径中，并使用特定于操作系统的分隔符将它们分开。 |
| [`IsAbs()`](https://www.geeksforgeeks.org/filepath-isabs-function-in-golang-with-examples/) | 这个函数用来检查路径是否是绝对的。 |
| [`Join()`](https://www.geeksforgeeks.org/filepath-join-function-in-golang-with-examples/) | 该函数用于将任意数量的路径元素连接到单个路径中，并使用特定于操作系统的分隔符将它们分开。 |
| `Match()` | 该函数用于检查名称是否与shell文件名模式匹配。 |
| `Rel()` | 此函数用于返回一个相对路径，当通过中间分隔符连接到`basepath`时，该路径在词汇上等同于`targpath`。 |
| `Split()` | 此函数用于在最后一个分隔符之后立即拆分路径，将其分成目录和文件名组件。 |
| `SplitList()` | 此函数用于拆分由特定于操作系统的列表分隔符连接的路径列表，通常在`PATH`或`GOPATH`环境变量中找到。 |
| `ToSlash()` | 此函数用于返回用斜杠（`/`）字符替换路径中每个分隔符的结果。 |
| `VolumeName()` | 该函数用于返回前导卷名。 |
| `Walk()` | 该函数用于遍历以`root`为根的文件树，为树中的每个文件或目录（包括根）调用`walkFn`。 |

## 示例

### 例1

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

**输出：**

```go
G/F/G
G/F/G
gfg/GFG
Geeks/for/Geeks
```

### 例2

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

**输出：**

```go
/home/gfg
.gfg
<nil>
/gfg
<nil>
/:gfg
<nil>
```