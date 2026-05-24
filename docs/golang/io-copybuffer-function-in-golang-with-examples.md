# io。Golang 中的 CopyBuffer()函数，示例

> 原文:[https://www . geesforgeks . org/io-copy buffer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-copybuffer-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的 **CopyBuffer()** 功能与 *Copy()方法*相同，但唯一的例外是，如果需要，它会通过提供的缓冲区显示，而不是分配临时缓冲区。如果 src 由 WriterTo 实现，或者 dst 由 ReaderFrom 实现，则不会使用缓冲区来执行复制操作。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func CopyBuffer(dst Writer, src Reader, buf []byte) (written int64, err error)

```

这里，“dst”是目的地，“src”是内容被复制到目的地的来源，“buf”是允许内存中有永久空间的缓冲区。

**返回值:**返回拷贝到“dst”的 int64 类型的字节总数，还返回从 src 拷贝到 dst 时遇到的第一个错误(如果有)。但是，如果缓冲区为零，则分配一个；否则，如果缓冲区的长度为零，则复制缓冲区会死机。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang program to illustrate the usage of
// io.CopyBuffer() function

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
    src := strings.NewReader("GfG\n")

    // Defining destination using Stdout
    dst := os.Stdout

    // Defining buffer of length one using
    // make keyword
    buffer := make([]byte, 1)

    // Calling CopyBuffer method with its parameters
    bytes, err := io.CopyBuffer(dst, src, buffer)

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
GfG
The number of bytes are: 4

```

**例 2:**

```go
// Golang program to illustrate the usage of
// io.CopyBuffer() function

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

    // Defining two sources
    src1 := strings.NewReader("GfG\n")
    src2 := strings.NewReader("GeeksforGeeks is a CS-Portal\n")

    // Defining destination using Stdout
    dst := os.Stdout

    // Defining buffer of length one using
    // make keyword
    buffer := make([]byte, 1)

    // Calling CopyBuffer method with its parameters
    bytes1, err := io.CopyBuffer(dst, src1, buffer)
    bytes2, err := io.CopyBuffer(dst, src2, buffer)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("The number of bytes are: %d\n", bytes1)
    fmt.Printf("The number of bytes are: %d\n", bytes2)
}
```

**输出:**

```go
GfG
GeeksforGeeks is a CS-Portal
The number of bytes are: 4
The number of bytes are: 29

```

这里，在上面的例子中，使用了 NewReader()方法，从这里读取要复制的内容。这里使用“Stdout”来创建一个默认的文件描述符，复制的内容将被写入其中。此外，在调用 CopyBuffer()方法时，上面重用了相同的缓冲区，不需要分配额外的缓冲区。