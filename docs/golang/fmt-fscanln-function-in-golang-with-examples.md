# fmt。Fscanln()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/fmt-fscanln-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-fscanln-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Fscanln()** 函数扫描指定的文本，从 r 中读取，然后将连续的空格分隔值存储到连续的参数中。该函数在换行符处停止扫描，在最后一项之后，必须有一个换行符或 EOF。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Fscanln(r io.Reader, a ...interface{}) (n int, err error)

```

**参数:**该函数接受两个参数，如下图所示:

*   **r io。阅读器:**该参数包含扫描的指定文本。
*   **a…接口{}:** 这些参数接受每个指定的元素。

**返回:**返回扫描成功的项目数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Fscanln() function

// Including the main package
package main

// Importing fmt, io and strings
import (
    "fmt"
    "io"
    "strings"
)

// Calling main
func main() {

    // Declaring list of strings,
    // integers and float value
    s := `gfg 9`

    // Calling NewReader() function for
    // reading each elements of the list
    // and then it place it into "r"
    r := strings.NewReader(s)

    // Declaring different types of variables
    var a string
    var b int

    for {

        // Calling Fscanln() function
        n, err := fmt.Fscanln(r, &a, &b)

        // Checking returned error is
        // end of the line (EOF) or not
        if err == io.EOF {
            break
        }

        // Checking if there is any error
        if err != nil {
            panic(err)
        }

        // Printing the number of items successfully
        // scanned and each elements too
        fmt.Printf("%d: %s, %d", n, a, b)
    }
}
```

**输出:**

```go
2: gfg, 9

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Fscanln() function

// Including the main package
package main

// Importing fmt, io and strings
import (
    "fmt"
    "io"
    "strings"
)

// Calling main
func main() {

    // Declaring list of strings,
    // integers and float value
    s := `gfg 9 true 5.78`

    // Calling NewReader() function for
    // reading each elements of the list
    // and then it place it into "r"
    r := strings.NewReader(s)

    // Declaring different types of variables
    var a string
    var b int
    var c bool
    var d float32

    for {

        // Calling Fscanln() function
        n, err := fmt.Fscanln(r, &a, &b, &c, &d)

        // Checking returned error is
        // end of the line (EOF) or not
        if err == io.EOF {
            break
        }

        // Checking if there is any error
        if err != nil {
            panic(err)
        }

        // Printing the number of items successfully
        // scanned and each elements too
        fmt.Printf("%d: %s, %d, %t, %g", n, a, b, c, d)
    }
}
```

**输出:**

```go
4: gfg, 9, true, 5.78

```