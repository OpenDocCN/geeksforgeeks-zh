# fmt。Golang 中的 Println()函数示例

> 原文:[https://www . geesforgeks . org/fmt-println-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-println-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Println()** 函数在 Go 语言格式中使用其操作数的默认格式，并写入标准输出。在这里，操作数之间总是加上空格，并在末尾追加一个换行符。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Println(a ...interface{}) (n int, err error)

```

这里，“a …interface{}”包含一些字符串，包括指定的常量变量。

**返回值:**返回写入的字节数和遇到的任何写入错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Println() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some const variables
    const name, dept = "GeeksforGeeks", "CS"

    // Calling Println() function
    fmt.Println(name, "is", "a", dept, "Portal.")

    // It is conventional not to worry about any
    // error returned by Println.

}
```

**输出:**

```go
GeeksforGeeks is a CS Portal.

```

在上面的代码中，可以看到函数 Println()在指定的字符串中没有包含任何空间，仍然在输出中是打印空间，这可以从上面的输出中看到。

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Println() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some const variables
    const num1, num2, num3, num4 = 5, 10, 15, 50

    // Calling Println() function
    fmt.Println(num1, "+", num2, "=", num3)
    fmt.Println(num1, "*", num2, "=", num4)

    // It is conventional not to worry about any
    // error returned by Println.

}
```

**输出:**

```go
5 + 10 = 15
5 * 10 = 50

```

在上面的代码中，可以看到函数 Println()没有使用任何换行符(\n)，仍然在输出中，它打印新的行，从上面显示的输出中可以看到。