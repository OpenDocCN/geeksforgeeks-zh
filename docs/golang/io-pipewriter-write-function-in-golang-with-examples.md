# io。用示例在 Golang 中编写()函数

> 原文:[https://www . geesforgeks . org/io-pipe writer-write-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-pipewriter-write-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。**管道工。Go 语言中的 Write()** 函数用于实现 Write 的标准接口。它将信息写入管道，并将其阻塞，直到一个或多个读取器已获取所有信息，或者管道的读取端已关闭。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func (w *PipeWriter) Write(data []byte) (n int, err error)

```

这里，“w”是指向 PipeWriter 的指针。其中 PipeWriter 是管道的写半部分，“数据”是写入数据的字节片。

**返回值:**返回写入的字节数和错误(如果有)。但是，如果管道的读取端因错误而关闭，则该错误将作为*错误*返回，否则返回的*错误*是错误关闭的管道错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.pipeWriter.Write() function

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

    // Defining data parameter of Read method
    data := make([]byte, 20)

    // Reading data into the buffer stated
    go func() {
        pipeReader.Read(data)

        // Closing read half of the pipe
        pipeReader.Close()
    }()

    // Using for loop
    for i := 0; i < 1; i++ {

        // Calling pipeWriter.Write() method
        n, err := pipeWriter.Write([]byte("GfG!"))

        // If error is not nil panic
        if err != nil {
            panic(err)
        }

        // Prints the content written
        fmt.Printf("%v\n", string(data))

        // Prints the number of bytes
        fmt.Printf("%v\n", n)
    }
}
```

**输出:**

```go
GfG!
4

```

这里，不返回错误，因为直到“for”循环运行，管道的读取端才关闭。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.pipeWriter.Write() function

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

    // Defining data parameter of Read method
    data := make([]byte, 20)

    // Reading data into the buffer stated
    go func() {
        pipeReader.Read(data)

        // Closing read half of the pipe
        pipeReader.Close()
    }()

    // Using for loop
    for i := 0; i < 2; i++ {

        // Calling pipeWriter.Write() method
        n, err := pipeWriter.Write([]byte("GfG!"))

        // If error is not nil panic
        if err != nil {
            panic(err)
        }

        // Prints the content written
        fmt.Printf("%v\n", string(data))

        // Prints the number of bytes
        fmt.Printf("%v\n", n)
    }
}
```

**输出:**

```go
GfG!
4
panic: io: read/write on closed pipe

goroutine 1 [running]:
main.main()
    /tmp/sandbox367087659/prog.go:38 +0x3ad

```

这里，当 for 循环第一次迭代后管道的读取端关闭时，将返回 ErrClosedPipe 错误。