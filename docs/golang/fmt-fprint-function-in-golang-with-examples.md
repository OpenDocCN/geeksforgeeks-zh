# fmt。Golang 中的 Fprint()函数示例

> 原文:[https://www . geesforgeks . org/fmt-fprint-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-fprint-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Fprint()** 函数在 Go 语言格式中使用其操作数的默认格式并写入 w。这里，当任何字符串未用作参数时，操作数之间会添加空格。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Fprint(w io.Writer, a ...interface{}) (n int, err error)

```

**参数:**该函数接受两个参数，如下图所示:

*   **w io。 Writer:** This is the specified standard input or output.
*   **A … interface {}:** This is used in code containing some strings or constant variables.

**返回值:**返回写入的字节数和遇到的任何写入错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Fprint() function

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

    // Calling Fprint() function which returns
    // "n" as the number of bytes written and 
    // "err" as any error ancountered
    n, err := fmt.Fprint(os.Stdout, name, " is a ",
                                dept, " portal.\n")

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

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Fprint() function

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
    const num1, num2, num3 = "a", "b", "c"

    // Calling Fprint() function which returns
    // "n" as the number of bytes written and
    // "err" as any error encountered
    n, err := fmt.Fprint(os.Stdout, num1, num2, num3, "\n")

    // Printing the number of bytes written
    fmt.Print(n, " bytes written.\n")

    // Printing if any error encountered
    fmt.Print(err)

}
```

**输出:**

```go
abc
4 bytes written.
<nil>

```

在上面的代码中，使用的常量变量是字符串，因此在输出中上面显示的两个字符串之间没有添加空格。

**例 3:**

```go
// Golang program to illustrate the usage of
// fmt.Fprint() function

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
    const num1, num2, num3 = 5, 15, 15

    // Calling Fprint() function which returns
    // "n" as the number of bytes written and 
    // "err" as any error encountered
    n, err := fmt.Fprint(os.Stdout, num1, num2, num3, "\n")

    // Printing the number of bytes written
    fmt.Print(n, " bytes written.\n")

    // Printing if any error encountered
    fmt.Print(err)

}
```

**输出:**

```go
5 15 15
8 bytes written.
<nil>

```

在上面的代码中，使用的常量变量是数字，因此在上面输出中显示的两个数字之间添加了空格。