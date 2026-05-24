# fmt。Golang 中的 Scanf()函数示例

> 原文:[https://www . geesforgeks . org/fmt-scanf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-scanf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Scanf()** 函数扫描标准输入中给出的输入文本，从中读取，并将连续的空格分隔值存储到由格式确定的连续参数中。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。
**语法:**

```go
func Scanf(format string, a ...interface{}) (n int, err error)
```

**参数:**该函数接受两个参数，如下图所示:

*   **格式字符串:**这是用于每个给定元素的不同格式。
*   **a…接口{}:** 这些参数接收每个给定的元素。

**返回:**返回扫描成功的项目数。
**例 1:**

## C

```go
// Golang program to illustrate the usage of
// fmt.Scanf() function

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

    // Calling Scanf() function for
    // scanning and reading the input
    // texts given in standard input
    fmt.Scanf("%s", &name)
    fmt.Scanf("%d", &alphabet_count)

    // Printing the given texts
    fmt.Printf("The word %s containing %d number of alphabets.",
               name, alphabet_count)

}
```

**输入:**

```go
GFG 3
```

**输出:**

```go
The word GFG containing 3 number of alphabets.
```

**例 2:**

## C

```go
// Golang program to illustrate the usage of
// fmt.Scanf() function

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
    var float_value float32
    var bool_value bool

    // Calling Scanf() function for
    // scanning and reading the input
    // texts given in standard input
    fmt.Scanf("%s", &name)
    fmt.Scanf("%d", &alphabet_count)
    fmt.Scanf("%g", &float_value)
    fmt.Scanf("%t", &bool_value)

    // Printing the given texts
    fmt.Printf("%s %d %g %t", name,
     alphabet_count, float_value, bool_value)

}
```

**输入:**

```go
GeeksforGeeks 13 6.789 true
```

**输出:**

```go
GeeksforGeeks 13 6.789 true
```