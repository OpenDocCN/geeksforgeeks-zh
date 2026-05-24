# fmt。Sscan()在 Golang 中的功能示例

> 原文:[https://www . geesforgeks . org/fmt-sscan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-sscan-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Sscan()** 函数扫描指定的文本，并将连续的空格分隔文本存储到连续的参数中。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Sscan(str string, a ...interface{}) (n int, err error)

```

**参数:**该函数接受两个参数，如下图所示:

*   **字符串:**此参数包含将要扫描的指定文本。
*   **a…界面{}:** 该参数接收各条文本。

**返回:**返回扫描成功的项目数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Sscan() function

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

    // Calling the Sscan() function which
    // returns the number of elements
    // successfully scanned and error if
    // it persists
    n, err := fmt.Sscan("GFG 3", &name, &alphabet_count)

    // Below statements get executed if there is any error
    if err != nil {
        panic(err)
    }

    // Printing the number of elements and each elements also
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
// fmt.Sscan() function

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

    // Calling the Sscan() function which
    // returns the number of elements
    // successfully scanned and error if
    // it persists
    n, err := fmt.Sscan("GeeksforGeeks 13 6.7 true", 
     &name, &alphabet_count, &float_value, &boolean_value)

    // Below statements get
    // executed if there is any error
    if err != nil {
        panic(err)
    }

    // Printing the number of 
    // elements and each elements also
    fmt.Printf("%d: %s, %d, %g, %t", n, name, 
     alphabet_count, float_value, boolean_value)

}
```

**输出:**

```go
4: GeeksforGeeks, 13, 6.7, true

```