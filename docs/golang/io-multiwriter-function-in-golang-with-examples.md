# io。Golang 中的 MultiWriter()函数及示例

> 原文:[https://www . geesforgeks . org/io-multi-writer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-multiwriter-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的 **MultiWriter()** 函数用于创建一个编写器，该编写器将其写操作复制到每个给定的编写器，这与 Unix 命令 tee(1)相同。在这里，每一篇文章都是写给每一个作者的，一个接一个。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func MultiWriter(writers ...Writer) Writer

```

这里，“writers”是在该函数中作为参数陈述的 writers 的数量。

**返回值:**它返回一个 Writer，该 Writer 包括所述缓冲区中存在的字节数，如果有错误，也返回一个错误。如果指定的写入程序返回一个错误，那么整个写入操作将停止，并且不会向下扩展列表。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.MultiWriter() function

// Including main package
package main

// Importing fmt, io, bytes, and strings
import (
    "bytes"
    "fmt"
    "io"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("Geeks")

    // Defining two buffers
    var buffer1, buffer2 bytes.Buffer

    // Calling MultiWriter method with its parameters
    writer := io.MultiWriter(&buffer1, &buffer2)

    // Calling Copy method with its parameters
    n, err := io.Copy(writer, reader)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Number of bytes in the buffer: %v\n", n)
    fmt.Printf("Buffer1: %v\n", buffer1.String())
    fmt.Printf("Buffer2: %v\n", buffer2.String())
}
```

**输出:**

```go
Number of bytes in the buffer: 5
Buffer1: Geeks
Buffer2: Geeks

```

这里，Copy()方法用于返回缓冲区中包含的字节数。这里两个缓冲区的内容是相同的，因为所述写入器将其写入复制到所有其他写入器。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.MultiWriter() function

// Including main package
package main

// Importing fmt, io, bytes, and strings
import (
    "bytes"
    "fmt"
    "io"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("GeeksforGeeks\nis\na\nCS-Portal!")

    // Defining two buffers
    var buffer1, buffer2 bytes.Buffer

    // Calling MultiWriter method with its parameters
    writer := io.MultiWriter(&buffer1, &buffer2)

    // Calling Copy method with its parameters
    n, err := io.Copy(writer, reader)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Number of bytes in the buffer: %v\n", n)
    fmt.Printf("Buffer1: %v\n", buffer1.String())
    fmt.Printf("Buffer2: %v\n", buffer2.String())
}
```

**输出:**

```go
Number of bytes in the buffer: 29
Buffer1: GeeksforGeeks
is
a
CS-Portal!
Buffer2: GeeksforGeeks
is
a
CS-Portal!

```