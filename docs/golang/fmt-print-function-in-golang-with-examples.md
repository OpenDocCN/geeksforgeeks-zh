# fmt.print()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/fmt-print-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-print-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。Go 语言格式的 **fmt.print()** 函数使用其操作数的默认格式，并写入标准输出。这里，当任何字符串未用作参数时，操作数之间会添加空格。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Print(a ...interface{}) (n int, err error)

```

这里的“a …interface{}”包含一些字符串和声明的常量变量。

**返回值:**返回写入的字节数和遇到的任何写入错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.print() function

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

    // Calling print() function
    fmt.Print(name, " is a ", dept, " portal.\n")

    // It is conventional not to worry about any
    // error returned by Print.

}
```

**输出:**

```go
GeeksforGeeks is a CS portal.

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.print() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some const variables
    const str1, str2, str3 = "a", "b", "c"

    // Calling print() function
    fmt.Print(str1, str2, str3, "\n")

    // It is conventional not to worry about any
    // error returned by Print.

}
```

**输出:**

```go
abc

```

在上面的代码中，使用的常量变量是字符串，因此在输出中上面显示的两个字符串之间没有添加空格。

**例 3:**

```go
// Golang program to illustrate the usage of
// fmt.print() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some const variables
    const num1, num2, num3 = 5, 15, 15

    // Calling print() function
    fmt.Print(num1, num2, num3, "\n")

    // It is conventional not to worry about any
    // error returned by Print.

}
```

**输出:**

```go
5 15 15

```

在上面的代码中，使用的常量变量是数字，因此在上面输出中显示的两个数字之间添加了空格。