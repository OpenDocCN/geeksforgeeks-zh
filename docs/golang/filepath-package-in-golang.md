# 戈朗的文件路径包

> 原文:[https://www.geeksforgeeks.org/filepath-package-in-golang/](https://www.geeksforgeeks.org/filepath-package-in-golang/)

Go 语言为实现实用程序提供了内置支持，这些实用程序在 filepath 包的帮助下以与目标操作系统定义的文件路径兼容的方式操作文件名路径。这个包使用正斜杠或反斜杠(取决于操作系统)来处理路径，例如，总是使用正斜杠的网址。

| 功能 | 描述 |
| **[腹肌](https://www.geeksforgeeks.org/filepath-abs-function-in-golang-with-examples/)T3】** | 此函数用于返回路径的绝对表示。 |
| **[基地](https://www.geeksforgeeks.org/filepath-base-function-in-golang-with-examples/)** | 该函数用于返回路径的最后一个元素。 |
| **[清洁](https://www.geeksforgeeks.org/filepath-clean-function-in-golang-with-examples/)** | 该函数用于通过纯词法处理返回与路径等价的最短路径名。 |
| **[目录](https://www.geeksforgeeks.org/filepath-dir-function-in-golang-with-examples/)** | 该函数用于返回除最后一个路径元素之外的所有元素，通常是路径的目录。 |
| **EvalSymlinks** | 此函数用于在评估任何符号链接后返回路径名。 |
| **[Ext](https://www.geeksforgeeks.org/filepath-ext-function-in-golang-with-examples/)** | 此函数用于返回 path 使用的文件扩展名。 |
| **FromSlash** | 此函数用于返回用分隔符替换路径中每个斜杠(“/”)字符的结果。 |
| **全球** | 该函数用于返回所有匹配模式的文件的名称，如果没有匹配的文件，则返回零。 |
| **已预备** | 它是为了历史兼容性而存在的，不应使用。 |
| **[【isabs】](https://www.geeksforgeeks.org/filepath-isabs-function-in-golang-with-examples/)** | 这个函数用来检查路径是否是绝对的。 |
| **[加入](https://www.geeksforgeeks.org/filepath-join-function-in-golang-with-examples/)** | 该函数用于将任意数量的路径元素连接到单个路径中，并使用特定于操作系统的分隔符将它们分开。 |
| **匹配** | 该函数用于检查名称是否与 shell 文件名模式匹配。 |
| 继电器 | 此函数用于返回一个相对路径，当通过中间分隔符连接到 basepath 时，该路径在词汇上等同于 targpath。 |
| **分裂** | 此函数用于在最后一个分隔符之后立即拆分路径，将其分成目录和文件名组件。 |
| **分裂列表** | 此函数用于拆分由特定于操作系统的列表分隔符连接的路径列表，通常在 PATH 或 GOPATH 环境变量中找到。 |
| **咳嗽** | 此函数用于返回用斜杠(“/”)字符替换路径中每个分隔符的结果。 |
| 体积名称 | 该函数用于返回前导卷名。 |
| **行走** | 该函数用于遍历以根为根的文件树，为树中的每个文件或目录(包括根)调用 walkFn。 |

**例 1 :**

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
/home/gfg /.gfg <nil>/gfg <nil>/:gfg</nil></nil> 
```