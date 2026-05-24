# io。Golang 中的 PipeReader . Close()函数示例

> 原文:[https://www . geesforgeks . org/io-piper reader-close-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-pipereader-close-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。**风笛手。Go 语言中的 Close()** 功能用于关闭阅读器。但是，对*管道写入器*的连续写入，即写入管道的一半，将返回 ErrClosedPipe 错误。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func (r *PipeReader) Close() error

```

这里，“r”是一个指向 PipeReader 的指针。其中 PipeReader 是管道的读半部分。

**返回值:**返回调用 Close 方法前写的内容。并且对*管道写入器*的连续写入，即写入管道的一半，将返回 ErrClosedPipe 错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.pipeReader.Close() function

// Including main package
package main

// Importing fmt and io
import (
    "fmt"
    "io"
)

// Calling main
func main() {

    // Calling Pipe method
    pipeReader, pipeWriter := io.Pipe()

    // Calling Write method in go function
    go func() {
        pipeWriter.Write([]byte("GfG"))
        pipeWriter.Write([]byte("GeeksforGeeks"))
        pipeWriter.Write([]byte("GfG is a CS-Portal."))
    }()

    // Creating buffer using make keyword
    // of specified length
    buffer := make([]byte, 50)

    // Using for loop
    for i := 0; i < 2; i++ {

        // Reading the contents in buffer
        n, err := pipeReader.Read(buffer)

        // If error is not nil panic
        if err != nil {
            panic(err)
        }

        // Calling Close method
        pipeReader.Close()

        // Prints the content read in buffer
        fmt.Printf("%s\n", buffer[:n])
    }
}
```

**输出:**

```go
GfG
panic: io: read/write on closed pipe

goroutine 1 [running]:
main.main()
    /tmp/sandbox180013044/prog.go:38 +0x302

```

这里，只返回一个写操作的内容，作为它在 Close()方法之前写入的内容，但是不返回在 Close 方法之后写入的内容，而是引发 ErrClosedPipe 错误。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.pipeReader.Close() function

// Including main package
package main

// Importing fmt and io
import (
    "fmt"
    "io"
)

// Calling main
func main() {

    // Calling Pipe method
    pipeReader, pipeWriter := io.Pipe()

    // Calling Write method in go function
    go func() {
        pipeWriter.Write([]byte("GfG"))
        pipeWriter.Write([]byte("GeeksforGeeks"))
        pipeWriter.Write([]byte("GfG is a CS-Portal."))
    }()

    // Creating buffer using make keyword
    // of specified length
    buffer := make([]byte, 50)

    // Calling Close method
    pipeReader.Close()

    // Using for loop
    for i := 0; i < 2; i++ {

        // Reading the contents in buffer
        n, err := pipeReader.Read(buffer)

        // If error is not nil panic
        if err != nil {
            panic(err)
        }

        // Prints the content read in buffer
        fmt.Printf("%s\n", buffer[:n])
    }
}
```

**输出:**

```go
panic: io: read/write on closed pipe

goroutine 1 [running]:
main.main()
    /tmp/sandbox881512815/prog.go:41 +0x2ea

```

这里，由于在任何读取操作之前都调用 Close()方法，所以不会将任何内容读入缓冲区，因此这里只会引发错误。