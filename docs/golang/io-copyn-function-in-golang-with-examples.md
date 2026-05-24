# io。Golang 中的 CopyN()函数示例

> 原文:[https://www . geesforgeks . org/io-copy n-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-copyn-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的 **CopyN()** 函数用于将“n”个字节从源复制到目标。如果 *dst* 是通过 *ReaderFrom* 接口实现的，那么副本就是利用它实现的。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func CopyN(dst Writer, src Reader, n int64) (written int64, err error)

```

这里，“dst”是目的地，“src”是内容从其复制到目的地的源，“n”是要从源复制的字节数的限制。

**返回值:**返回拷贝到“dst”的 int64 类型的字节总数，还返回从 src 拷贝到 dst 时遇到的第一个错误(如果有)。此外，当且仅当错误为“无”时，返回的字节数为“n”。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang program to illustrate the usage of
// io.CopyN() function

// Including main package
package main

// Importing fmt, io, os, and strings
import (
    "fmt"
    "io"
    "os"
    "strings"
)

// Calling main
func main() {

    // Defining source
    src := strings.NewReader("GeeksforGeeks\n")

    // Defining destination using Stdout
    dst := os.Stdout

    // Calling CopyN method with its parameters
    bytes, err := io.CopyN(dst, src, 5)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("\nThe number of bytes are: %d\n", bytes)
}
```

**输出:**

```go
Geeks
The number of bytes are: 5

```

这里，返回的字节数等于“n”，因为错误是“零”。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.CopyN() function

// Including main package
package main

// Importing fmt, io, os, and strings
import (
    "fmt"
    "io"
    "os"
    "strings"
)

// Calling main
func main() {

    // Defining source
    src := strings.NewReader("CS-Portal\n")

    // Defining destination using Stdout
    dst := os.Stdout

    // Calling CopyN method with its parameters
    bytes, err := io.CopyN(dst, src, 20)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("The number of bytes are: %d\n", bytes)
}
```

**输出:**

```go
CS-Portal
panic: EOF

goroutine 1 [running]:
main.main()
    /tmp/sandbox691649995/prog.go:29 +0x137

```

这里，在上面的例子中，使用了 NewReader()方法，从这里读取要复制的内容。这里使用“Stdout”来创建一个默认的文件描述符，复制的内容将被写入其中。此外，这里返回的字节数小于“n”，所以上面抛出了一个 EOF 错误。