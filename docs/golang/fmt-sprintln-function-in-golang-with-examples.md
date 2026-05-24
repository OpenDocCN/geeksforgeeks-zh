# fmt。Golang 中的 Sprintln()函数示例

> 原文:[https://www . geesforgeks . org/fmt-sprint ln-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-sprintln-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。函数在 Go 语言格式中使用其操作数的默认格式，并返回结果字符串。在这里，操作数之间总是加上空格，并在末尾追加一个换行符。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。**

**语法:**

```go
func Sprintln(a ...interface{}) string

```

这里，“a …interface{}”包含一些字符串和指定的常量变量。

**返回:**返回结果字符串。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Sprintln() function

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

    // Calling Sprintln() function
    s := fmt.Sprintln(name, "is a", dept, "Portal.")

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
// fmt.Sprintln() function

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
    const num1, num2, num3, num4 = 5, 10, 15, 50

    // Calling Sprintln() function
    s1 := fmt.Sprintln(num1, "+", num2, "=", num3)
    s2 := fmt.Sprintln(num1, "*", num2, "=", num4)

    // Calling WriteString() function to write the
    // contents of the string "s1" and "s2" to "os.Stdout"
    io.WriteString(os.Stdout, s1)
    io.WriteString(os.Stdout, s2)

}
```

**输出:**

```go
5 + 10 = 15
5 * 10 = 50

```

在上面的代码中，没有使用新的行或空格，但是这个函数在操作数之间添加了新的行和空格，可以在上面的输出中看到。