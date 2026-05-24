# fmt。Golang 中的 Scan()函数示例

> 原文:[https://www . geesforgeks . org/fmt-scan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-scan-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Scan()** 函数扫描标准输入中给出的输入文本，从中读取，并将连续的空格分隔值存储到连续的参数中。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Scan(a ...interface{}) (n int, err error)
```

在这里，“a …interface{}”接收每种给定文本。
**返回:**返回成功扫描的物品数量。

**例 1:**

## C

```go
// Golang program to illustrate the usage of
// fmt.Scan() function

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

    // Calling Scan() function for
    // scanning and reading the input
    // texts given in standard input
    fmt.Scan(&name)
    fmt.Scan(&alphabet_count)

    // Printing the given texts
    fmt.Printf("The word %s containing %d number of alphabets.",
               name, alphabet_count)

}
```