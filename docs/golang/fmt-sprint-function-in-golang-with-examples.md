# fmt。Golang 中的 Sprint()函数示例

> 原文:[https://www . geesforgeks . org/fmt-sprint-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-sprint-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Sprint()** 函数在 Go 语言格式中使用其操作数的默认格式，并返回结果字符串。这里，当任何字符串未用作常量变量时，操作数之间会添加空格。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Sprint(a ...interface{}) string

```

这里，“a …interface{}”包含一些字符串，包括指定的常量变量。

**返回:**返回结果字符串。

**例 1:**

```go
// Golang program to illustrate the usage of
// fmt.Sprint() function

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

    // Calling Sprint() function
    s := fmt.Sprint(name, " is a ", dept, " Portal.\n")

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
// fmt.Sprint() function

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

    // Calling Sprint() function
    s := fmt.Sprint(num1, num2, num3)

    // Calling WriteString() function to write the
    // contents of the string "s" to "os.Stdout"
    io.WriteString(os.Stdout, s)

}
```

**输出:**

```go
5 10 15

```

在上面的代码中，可以看到函数 Sprint()没有使用任何空格，在数字之间的输出中仍然可以看到空格，因为函数本身添加了空格，因为没有一个字符串用作常量变量。

**例 3:**

```go
// Golang program to illustrate the usage of
// fmt.Sprint() function

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
    const str1, str2, str3 = "a", "b", "c"

    // Calling Sprint() function
    s := fmt.Sprint(str1, str2, str3)

    // Calling WriteString() function to write the
    // contents of the string "s" to "os.Stdout"
    io.WriteString(os.Stdout, s)

}
```

**输出:**

```go
abc

```

在上面的代码中，可以看到函数 Sprint()没有使用任何空格，在两个字母之间的输出中也看不到空格，这是因为常量变量中使用了字符串。