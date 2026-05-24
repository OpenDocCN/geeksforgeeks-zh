# Golang 中的

# io.WriteString()函数，示例为

> Original: [https://www.geeksforgeeks.org/io-writestring-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-writestring-function-in-golang-with-examples/)

在 GO 语言中，*io*包为 I/O 原语提供基本接口。 它的主要工作是封装这种原语之王的正在进行的实现。 GO 语言中的**WriteString()**函数用于将所述字符串“s”的内容写入编写器“w”，该编写器获取一片字节。 如果“w”是由*StringWriter*实现的，则立即调用其*WriteString*方法。 否则，w.Write 被严格调用一次。 此外，该函数在 io 包下定义。 在这里，您需要导入“io”包才能使用这些函数。

**语法：**

```go
func WriteString(w Writer, s string) (n int, err error)

```

这里，“w”是编写器，“s”是写给编写器的字符串。

**返回值：**它返回 int 类型内容的总字节数，如果有错误，也会返回错误。

以下示例说明了上述方法的使用：

**示例 1：**

```go
// Golang program to illustrate the usage of
// io.WriteString() function

// Including main package
package main

// Importing fmt, io, and os
import (
    "fmt"
    "io"
    "os"
)

// Calling main
func main() {

    // Defining w using Stdout
    w := os.Stdout

    // Calling WriteString method with its parameters
    n, err := io.WriteString(w, "GfG\n")

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("n: %d\n", n)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// io.WriteString() function

// Including main package
package main

// Importing fmt, io, and os
import (
    "fmt"
    "io"
    "os"
)

// Calling main
func main() {

    // Defining w using Stdout
    w := os.Stdout

    // Calling WriteString method with its parameters
    n, err := io.WriteString(w, "GeeksforGeeks\nis\na\nCS-Portal.\n")

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("n: %d\n", n)
}
```

发帖主题：Re：Колибри0.7.8.0

这里，在上面的示例中，使用“stdout”来创建一个默认文件描述符，其中写入了所述内容。