# fmt。Golang 中的 Errorf()函数示例

> 原文:[https://www . geesforgeks . org/fmt-error f-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-errorf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Go 语言中的 Errorf()** 函数允许我们使用格式化功能来创建描述性错误消息。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Errorf(format string, a ...interface{}) error

```

**参数:**该函数接受两个参数，如下图所示:

*   **字符串:**这是带有占位符值的错误消息，例如字符串为%s，整数为%d。
*   **a …interface{}:** 这要么是代码中使用的常量变量名，要么是任何内置函数。

**返回值:**返回满足错误的字符串值。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Errorf() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some constant variables
    const name, dept = "GeeksforGeeks", "CS"

    // Calling the Errorf() function with verb
    // %q which is used for a single-quoted character
    err := fmt.Errorf("%q is a %q Portal.", name, dept)

    // Printing the error message
    fmt.Println(err.Error())
}
```

**输出:**

```go
"GeeksforGeeks" is a "CS" Portal.

```

**例 2:**

```go
// Golang program to illustrate the usage of
// fmt.Errorf() function

// Including the main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Calling Errorf() function with verb $v which is used
    // for printing structs
    err := fmt.Errorf("error occurred at: %v", time.Now())

    // Printing the error
    fmt.Println("An error happened:", err)
}
```

**输出:**

```go
An error happened: error occurred at: 2009-11-10 23:00:00 +0000 UTC m=+0.000000001

```