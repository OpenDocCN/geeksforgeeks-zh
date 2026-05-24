# fmt。Fscan()在 Golang 中的功能示例

> 原文:[https://www . geesforgeks . org/fmt-fscan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-fscan-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Fscan()** 函数扫描指定的文本，从 r 中读取，然后将连续的空格分隔值存储到连续的参数中。在这里，换行符被算作空格。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Fscan(r io.Reader, a ...interface{}) (n int, err error)

```

**参数:**该函数接受两个参数，如下图所示:

*   **r io。阅读器:**该参数包含扫描的指定文本。
*   **a…界面{}:** 该参数接收每种类型的指定文本。

**返回:**返回扫描成功的项目数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Fscan() function

// Including the main package
package main

// Importing fmt, io and strings
import (
    "fmt"
    "os"
    "strings"
)

// Calling main
func main() {

        // Declaring some type of variables
    var (
        i int
        b bool
        s string
    )

    // Calling the NewReader() function to
    // specify some type of texts.
    // variable "r" contains the scanned texts
    r := strings.NewReader("10 false GFG")

    // Calling the Fscan() function to receive 
    // the scanned texts
    n, err := fmt.Fscan(r, &i, &b, &s)

    // If the above function returns an error then
    // below statement will be executed
    if err != nil {
        fmt.Fprintf(os.Stderr, "Fscanf: %v\n", err)
    }

    // Printing each type of scanned texts
    fmt.Println(i, b, s)

    // It returns the number of items 
    // successfully scanned
    fmt.Println(n)
}
```

**输出:**

```go
10 false GFG
3

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Fscan() function

// Including the main package
package main

// Importing fmt, io and strings
import (
    "fmt"
    "os"
    "strings"
)

// Calling main
func main() {

        // Declaring some type of variables
    var (
        i int
        b bool
        s string
        f float32
    )

    // Calling the NewReader() function to
    // specify some type of texts.
    // variable "r" contains the scanned texts
    r := strings.NewReader("46 true 3.4 GeeksforGeeks")

    // Calling the Fscan() function to receive 
    // the scanned texts
    n, err := fmt.Fscan(r, &i, &b, &f, &s)

    // If the above function returns an error then
    // below statement will be executed
    if err != nil {
        fmt.Fprintf(os.Stderr, "Fscanf: %v\n", err)
    }

    // Printing each type of scanned texts
    fmt.Println(i, b, f, s)

    // It returns the number of items 
    // successfully scanned
    fmt.Println(n)
}
```

**输出:**

```go
46 true 3.4 GeeksforGeeks
4

```