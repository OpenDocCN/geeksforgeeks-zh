# io。Golang 中的 Close()函数示例

> 原文:[https://www . geesforgeks . org/io-pipe writer-close-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-pipewriter-close-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。**管道工。Go 语言中的 Close()** 功能用于关闭编写器。但是，从*管道头*连续读取，即读取管道的一半，不会返回任何字节，并且会返回一个 EOF 错误。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func (w *PipeWriter) Close() error

```

这里，“w”是指向 PipeWriter 的指针。其中 PipeWriter 是管道的写半部分。

**返回值:**返回 Close 方法之前写的内容。并且从*管道头*连续读取，即读取管道的一半，在调用 Close()方法后不会返回任何字节，并且会返回一个 EOF 错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.PipeWriter.Close() function

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

    // Calling Close method in go function after
    // two Write operations
    go func() {
        pipeWriter.Write([]byte("GfG"))
        pipeWriter.Write([]byte("GeeksforGeeks"))
        pipeWriter.Close()

        // Again calling Write method
        pipeWriter.Write([]byte("GfG is a CS-Portal."))
    }()

    // Creating buffer using make keyword
    // of specified length
    buffer := make([]byte, 50)

    // Using for loop
    for i := 0; i < 4; i++ {

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
GfG
GeeksforGeeks
panic: EOF

goroutine 1 [running]:
main.main()
    /tmp/sandbox342418232/prog.go:42 +0x2d1

```

在这里，两个写操作的内容会像在 Close()方法之前写的那样返回，但是在 Close 方法之后写的内容不会返回，而是抛出一个 EOF 错误。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.PipeWriter.Close() function

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

    // Calling Close method in go function
    go func() {
        pipeWriter.Close()

        // Calling Write method
        pipeWriter.Write([]byte("GfG is a CS-Portal."))
    }()

    // Creating buffer using make keyword
    // of specified length
    buffer := make([]byte, 50)

    // Using for loop
    for i := 0; i < 4; i++ {

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
panic: EOF

goroutine 1 [running]:
main.main()
    /tmp/sandbox173042396/prog.go:40 +0x2d1

```

这里，在 Close 方法之前不执行写操作，因此不返回任何内容，并且抛出一个 EOF 错误。