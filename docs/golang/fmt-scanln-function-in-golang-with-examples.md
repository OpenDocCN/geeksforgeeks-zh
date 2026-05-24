# fmt。示例中的 Scanln()函数

> 原文:[https://www . geesforgeks . org/fmt-scanln-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-scanln-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Scanln()** 函数扫描标准输入中给出的输入文本，从那里读取，并将连续的空格分隔值存储到连续的参数中。该函数在换行符处停止扫描，在最后一项之后，必须有一个换行符或 EOF。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Scanln(a ...interface{}) (n int, err error)

```

在这里，“一个…接口{}”接收每个给定的文本。

**返回:**返回扫描成功的项目数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Scanln() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some variables
    var name string
    var alphabet_count int

    // Calling Scanln() function for
    // scanning and reading the input
    // texts given in standard input
    fmt.Scanln(&name)
    fmt.Scanln(&alphabet_count)

    // Printing the given texts
    fmt.Printf("%s %d", 
               name, alphabet_count)

}
```

**输入:**

```go
GFG 3

```

**输出:**

```go
GFG 0

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Scanln() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some variables
    var name string
    var alphabet_count int

    // Calling Scanln() function for
    // scanning and reading the input
    // texts given in standard input
    fmt.Scanln(&name)
    fmt.Scanln(&alphabet_count)

    // Printing the given texts
    fmt.Printf("%s %d", 
               name, alphabet_count)

}
```

**输入:**

```go
GeeksforGeeks \n 13

```

**输出:**

```go
GeeksforGeeks 0

```

在上面的例子中，可以看到标准输入取“GeeksforGeeks \n 13”的值，但是它返回的输出是“GeeksforGeeks 0”这是因为这个函数停止扫描新行(\n)。