# fmt。Fscanf()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/fmt-fscanf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-fscanf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Fscanf()** 函数扫描指定的文本，从 r 中读取，然后将连续的空格分隔值存储到由格式确定的连续参数中。这里，输入中的换行符必须与格式中的换行符匹配。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Fscanf(r io.Reader, format string, a ...interface{}) (n int, err error)

```

**参数:**该函数接受三个参数，如下图所示:

*   **r io。阅读器:**该参数包含扫描的指定文本。
*   **格式字符串:**该参数包含接收元素的不同格式。
*   **a …interface{}:** 此参数是每个元素的指定变量。

**返回:**返回解析成功的项数。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Fscanf() function

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

    // Calling the Fscanf() function to receive 
    // the scanned texts
    n, err := fmt.Fscanf(r, "%d %t %s", &i, &b, &s)

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
// fmt.Fscanf() function

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

    // Calling the Fscanf() function to receive 
    // the scanned texts
    n, err := fmt.Fscanf(r, "%d %t %g %s", &i, &b, &f, &s)

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