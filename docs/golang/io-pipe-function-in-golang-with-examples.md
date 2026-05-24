# io。Golang 中的 Pipe()函数示例

> 原文:[https://www . geesforgeks . org/io-pipe-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-pipe-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的**管道()**函数用于创建一个并发的内存管道，并可用于链接需要 *io 的代码。读取器*的代码需要一个 *io。编剧*。这里，管道上的*读*和*写*是一对一配对的，除非需要多个“读”进行单个“写”。这表明对*管道写入器*的每一次写入都将停止，直到它从完全获取写入数据的*管道读取器*完成一次或多次读取。

但是，数据会从写入直接跟踪到相关的读取，内部没有缓冲。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func Pipe() (*PipeReader, *PipeWriter)

```

这里，“PipeReader”是指向 PipeReader 的指针。其中 PipeReader 是管道的读取部分，“PipeWriter”是指向 PipeWriter 的指针。其中 PipeWriter 是管道的写半部分。

**返回值:**返回一个指向管道头和管道写器的指针。

**注意:**同时调用读写或者关闭是安全的。但是，对读取的并行调用和对写入的并行调用也是安全的。单独的呼叫将按顺序关闭。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.Pipe() function

// Including main package
package main

// Importing fmt, io, and bytes
import (
    "bytes"
    "fmt"
    "io"
)

// Calling main
func main() {

    // Calling Pipe method
    pipeReader, pipeWriter := io.Pipe()

    // Using Fprint in go function to write
    // data to the file
    go func() {
        fmt.Fprint(pipeWriter, "Geeks\n")

        // Using Close method to close write
        pipeWriter.Close()
    }()

    // Creating a buffer
    buffer := new(bytes.Buffer)

    // Calling ReadFrom method and writing
    // data into buffer
    buffer.ReadFrom(pipeReader)

    // Prints the data in buffer
    fmt.Print(buffer.String())
}
```

**输出:**

```go
Geeks

```

**例 2:**

```go
// Golang program to illustrate the usage of
// io.Pipe() function

// Including main package
package main

// Importing fmt, io, and bytes
import (
    "bytes"
    "fmt"
    "io"
)

// Calling main
func main() {

    // Calling Pipe method
    pipeReader, pipeWriter := io.Pipe()

    // Using Fprint in go function to write
    // data to the file
    go func() {
        fmt.Fprint(pipeWriter, "GeeksforGeeks\nis\na\nCS-Portal.\n")

        // Using Close method to close write
        pipeWriter.Close()
    }()

    // Creating a buffer
    buffer := new(bytes.Buffer)

    // Calling ReadFrom method and writing
    // data into buffer
    buffer.ReadFrom(pipeReader)

    // Prints the data in buffer
    fmt.Print(buffer.String())
}
```

**输出:**

```go
GeeksforGeeks
is
a
CS-Portal.

```