# fmt。Golang 中的 Sprintf()函数示例

> 原文:[https://www . geesforgeks . org/fmt-sprintf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-sprintf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Sprintf()** 函数根据格式说明符格式化并返回结果字符串。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Sprintf(format string, a ...interface{}) string

```

**参数:**该函数接受两个参数，如下图所示:

*   **格式字符串:**这包括一些变量和一些字符串。
*   **a…接口{}:** 这是指定的常量变量。

**返回:**返回结果字符串。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Sprintf() function

// Including the main package
package main

// Importing fmt, io and os
import (
    "fmt"
    "io"
    "os"
)

// Calling main
func main() {

    // Declaring some const variables
    const name, dept = "GeeksforGeeks", "CS"

    // Calling Sprintf() function
    s := fmt.Sprintf("%s is a %s Portal.\n", name, dept)

    // Calling WriteString() function to write the
    // contents of the string "s" to "os.Stdout"
    io.WriteString(os.Stdout, s)

}
```

**输出:**

```go
GeeksforGeeks is a CS Portal.

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Sprintf() function

// Including the main package
package main

// Importing fmt, io and os
import (
    "fmt"
    "io"
    "os"
)

// Calling main
func main() {

    // Declaring some const variables
    const num1, num2, num3 = 5, 10, 15

    // Calling Sprintf() function
    s := fmt.Sprintf("%d + %d = %d", num1, num2, num3)

    // Calling WriteString() function to write the
    // contents of the string "s" to "os.Stdout"
    io.WriteString(os.Stdout, s)

}
```

**输出:**

```go
5 + 10 = 15

```