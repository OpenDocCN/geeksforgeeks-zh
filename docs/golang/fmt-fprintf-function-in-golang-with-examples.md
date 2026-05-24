# fmt。Golang 中的 Fprintf()函数示例

> 原文:[https://www . geesforgeks . org/fmt-fprintf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-fprintf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Fprintf()** 函数在 Go 语言中根据格式说明符格式化并写入 w，而且这个函数是在 fmt 包下定义的。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Fprintf(w io.Writer, format string, a ...interface{}) (n int, err error)
```

**参数:**该功能接受三个参数，如下图所示-

*   **w io。Writer:** 这是指定的标准输入或输出。
*   **格式字符串:**这是包含动词在内的一些字符串。
*   **a …interface{}:** 这是代码中使用的指定常量变量。

**返回值:**返回写入的字节数和遇到的任何写入错误。
**例 1:**

## C

```go
// Golang program to illustrate the usage of
// fmt.Fprintf() function

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

    // Calling Fprintf() function which returns
    // "n" as the number of bytes written and
    // "err" as any error ancountered
    n, err := fmt.Fprintf(os.Stdout, "%s is a %s portal.\n",
                                                name, dept)

    // Printing the number of bytes written
    fmt.Print(n, " bytes written.\n")

    // Printing if any error encountered
    fmt.Print(err)

}
```