# 格朗的包裹

> 原文:[https://www.geeksforgeeks.org/packages-in-golang/](https://www.geeksforgeeks.org/packages-in-golang/)

包是 Go 语言中最强大的部分。包的目的是通过将相关功能组合成单个单元来设计和维护大量程序，以便它们易于维护和理解，并且独立于其他包程序。这种模块化允许他们共享和重用。在 Go 语言中，每个包都用不同的名称定义，这个名称与它们的功能很接近，就像“字符串”包一样，它包含只与字符串相关的方法和函数。

### 要点

**1。导入路径:**在 Go 语言中，每个包都由一个唯一的字符串定义，这个字符串称为导入路径。借助导入路径，您可以在程序中导入包。例如:

```go
import "fmt"
```

此声明表明您正在程序中导入 fmt 包。包的导入路径是全局唯一的。为了避免不同于标准库的包路径之间的冲突，包路径应该以拥有或托管包的组织的 internet 域名开头。例如:

```go
import "geeksforgeeks.com/example/strings"
```

**2。包声明:**在 Go 语言中，包声明始终出现在源文件的开头，此声明的目的是在该包被另一个包导入时确定该包的默认标识符。例如:

```go
package main
```

**3。进口申报:**进口申报紧接包裹申报之后。Go 源文件包含零个或多个导入声明，每个导入声明在括号中指定一个或多个包的路径。例如:

```go
// Importing single package
import "fmt"

// Importing multiple packages
import(
"fmt"
"strings"
"bytes"
) 

```

当您在程序中导入包时，您可以访问该包的成员。例如，我们有一个名为“sort”的包，因此当您在程序中导入这个包时，您可以访问 sort。Float64s()，排序。该包的 SearchStrings()等函数。

**4。空白导入:**在 Go 编程中，有时我们会在程序中导入一些包，但在程序中并不使用。当您运行包含未使用的包的这类程序时，编译器会给出一个错误。因此，为了避免这个错误，我们在包的名称前使用一个空白标识符。例如:

```go
import _ "strings"
```

它被称为空白导入。当主程序可以在编译时启用空白导入附加包所提供的可选功能时，会在许多或某些情况下使用它。

**5。嵌套包:**在 Go 语言中，只需创建一个子目录，就可以在另一个包中创建一个包。嵌套包可以像根包一样导入。例如:

```go
import "math/cmplx"
```

这里，数学包是主包，cmplx 包是嵌套包。

**6。**有时有些包可能同名，但这类包的路径总是不同的。例如，数学和加密包都包含一个名为 rand 的包，但该包的路径不同，即数学/rand 和加密/rand。

**7。**在 Go 编程中，为什么主包总是出现在程序的顶部？因为主包告诉 go build 它必须激活链接器来生成一个可执行文件。

### 给包命名

在 Go 语言中，当您命名包时，必须始终遵循以下几点:

*   创建包时，包的名称必须简短。例如字符串、时间、标志等。是标准库包。
*   包名应该是描述性的和明确的。
*   始终尽量避免选择常用的或用于局部相对变量的名称。
*   包装的名称一般以单数形式出现。有时一些包以复数形式命名，如字符串、字节、缓冲区等。因为为了避免与关键字冲突。
*   始终避免使用已经有其他含义的包装名称。例如:

**示例:**

```go
// Go program to illustrate the
// concept of packages
// Package declaration
package main

// Importing multiple packages
import (
    "bytes"
    "fmt"
    "sort"
)

func main() {

    // Creating and initializing slice
    // Using shorthand declaration
    slice_1 := []byte{'*', 'G', 'e', 'e', 'k', 's', 'f',
        'o', 'r', 'G', 'e', 'e', 'k', 's', '^', '^'}
    slice_2 := []string{"Gee", "ks", "for", "Gee", "ks"}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1 : %s", slice_1)
    fmt.Println("\nSlice 2: ", slice_2)

    // Trimming specified leading
    // and trailing Unicode points
    // from the given slice of bytes
    // Using Trim function
    res := bytes.Trim(slice_1, "*^")
    fmt.Printf("\nNew Slice : %s", res)

    // Sorting slice 2
    // Using Strings function
    sort.Strings(slice_2)
    fmt.Println("\nSorted slice:", slice_2)
}
```

**输出:**

```go
Original Slice:
Slice 1 : *GeeksforGeeks^^
Slice 2:  [Gee ks for Gee ks]

New Slice : GeeksforGeeks
Sorted slice: [Gee Gee for ks ks]

```