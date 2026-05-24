# fmt。Sscanln()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/fmt-sscanln-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-sscanln-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Sscanln()** 函数扫描指定的字符串，并将连续的空格分隔值存储到连续的参数中。该函数在换行符处停止扫描，在最后一项之后，必须有一个换行符或 EOF。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Sscanln(str string, a ...interface{}) (n int, err error)

```

**参数:**该函数接受两个参数，如下图所示:

*   **String:** This parameter contains the specified text to be scanned.
*   **A … interface {}:** This parameter receives each element of the string.

**返回:**返回扫描成功的项目数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Sscanln() function

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

    // Calling Sscanln() function
    n, err := fmt.Sscanln("GFG 3", &name, &alphabet_count)

    // Checking if the function
    // returns any error
    if err != nil {
        panic(err)
    }

    // Printing the number of elements 
    // present in the specified string
    // and also the elements
    fmt.Printf("n: %d, name: %s, alphabet_count: %d",
                             n, name, alphabet_count)

}
```

**输出:**

```go
n: 2, name: GFG, alphabet_count: 3

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Sscanln() function

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

    // Calling Sscanln() function
    fmt.Sscanln("GFG \n 3", &name, &alphabet_count)

    // Printing the elements of the string
    fmt.Printf("name: %s, alphabet_count: %d", name, alphabet_count)

}
```

**输出:**

```go
name: GFG, alphabet_count: 0

```

在上面的例子中，可以看到 alphabet_count 的赋值是 3，但输出仍然是 0，这是因为在两个元素“GFG”和“alphabet_count”之间有一个新行(\n)，因此该函数在换行符处停止扫描。