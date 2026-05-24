# fmt。Sscanf()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/fmt-ss canf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-sscanf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Sscanf()** 函数扫描指定的字符串，并将连续的空格分隔值存储到由格式确定的连续参数中。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Sscanf(str string, format string, a ...interface{}) (n int, err error)

```

**参数:**该函数接受三个参数，如下图所示:

*   **字符串:**此参数包含将要扫描的指定文本。
*   **格式字符串:**此参数是指定字符串的每个元素的不同格式类型。
*   **a …interface{}:** 此参数接收字符串的每个元素。

**返回:**返回解析成功的项数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Sscanf() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring two variables
    var name string
    var alphabet_count int

    // Calling the Sscanf() function which
    // returns the number of elements
    // successfully parsed and error if
    // it persists
    n, err := fmt.Sscanf("GFG is having 3 alphabets.",
      "%s is having %d alphabets.", &name, &alphabet_count)

    // Below statements get 
    // executed if there is any error
    if err != nil {
        panic(err)
    }

    // Printing the number of 
    // elements and each elements also
    fmt.Printf("%d: %s, %d\n", n, name, alphabet_count)

}
```

**输出:**

```go
2: GFG, 3

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Sscanf() function

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
    var boolean_value bool

    // Calling the Sscanf() function which
    // returns the number of elements
    // successfully parsed and error if
    // it persists
    n, err := fmt.Sscanf("GeeksforGeeks 13 6.7 true",
               "%s %d %g %t", &name, &alphabet_count, 
                        &float_value, &boolean_value)

    // Below statements get executed
    // if there is any error
    if err != nil {
        panic(err)
    }

    // Printing the number of elements
    // and each elements also
    fmt.Printf("%d: %s, %d, %g, %t", n, name,
      alphabet_count, float_value, boolean_value)

}
```

**输出:**

```go
4: GeeksforGeeks, 13, 6.7, true

```