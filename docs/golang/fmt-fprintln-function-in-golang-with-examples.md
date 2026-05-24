# fmt。Fprintln()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/fmt-fprintln-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-fprintln-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Fprintln()** 函数在 Go 语言格式中使用其操作数的默认格式并写入 w。这里，在指定的操作数之间总是添加空格，并在末尾追加一个换行符。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Fprintln(w io.Writer, a ...interface{}) (n int, err error)

```

**参数:**该函数接受两个参数，如下图所示:

*   **w io。 Writer:** This is the specified standard input or output.
*   **A … interface {}:** This is used in the code containing some strings and constant variables.

**返回值:**返回写入的字节数和遇到的任何写入错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Fprintln() function

// Including the main package
package main

// Importing fmt and os
import (
    "fmt"
    "os"
)

// Calling main
func main() {

    // Declaring some const variables
    const name, dept = "GeeksforGeeks", "CS"

    // Calling Fprintln() function which returns
    // "n" as the number of bytes written and
    // "err" as any error ancountered
    n, err := fmt.Fprintln(os.Stdout, name, 
                   "is a", dept, "portal.")

    // Printing the number of bytes written
    fmt.Print(n, " bytes written.\n")

    // Printing if any error encountered
    fmt.Print(err)

}
```

**输出:**

```go
GeeksforGeeks is a CS portal.
30 bytes written.
<nil>

```

在上面的代码中，可以看到在 Fprintln()函数中，没有添加换行符(\n)，但是它打印了一个新的行，这可以从上面显示的输出中看到。

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Fprintln() function

// Including the main package
package main

// Importing fmt and os
import (
    "fmt"
    "os"
)

// Calling main
func main() {

    // Declaring some const variables
    const str1, str2, str3 = "a", "b", "c"

    // Calling Fprintln() function which returns
    // "n" as the number of bytes written and
    // "err" as any error ancountered
    n, err := fmt.Fprintln(os.Stdout, str1, str2, str3)

    // Printing the number of bytes written
    fmt.Print(n, " bytes written.\n")

    // Printing if any error encountered
    fmt.Print(err)

}
```

**输出:**

```go
a b c
6 bytes written.
<nil>

```

在上面的代码中，可以看到，在 Fprintln()函数中，没有添加空格，但它仍然打印包括空格在内的内容，这可以从上面显示的输出中看到。