# io。PipeReader .用示例读取 Golang 中的()函数

> 原文:[https://www . geesforgeks . org/io-piper reader-read-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-pipereader-read-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。**风笛手。Go 语言中的 Read()** 函数用于实现 Read 的标准接口。它从管道中读取信息并阻止它，直到写入器出现或管道的写入端关闭。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func (r *PipeReader) Read(data []byte) (n int, err error)

```

这里，“r”是一个指向 PipeReader 的指针。其中，PipeReader 是管道的读取部分，“数据”是指定长度的字节片，写入的数据被读入其中。

**返回值:**返回读取的字节数和错误(如果有)。但是，如果管道的写入端因错误而关闭，则该错误将作为*错误*返回，否则返回的*错误*是电渗流错误。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.PipeReader.Read() function

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

    // Writing data to the pipe
    go func() {
        pipeWriter.Write([]byte("GfG"))
        pipeWriter.Write([]byte("GeeksforGeeks"))
        pipeWriter.Write([]byte("GfG is a CS-Portal."))

        // Closing write half of the pipe
        pipeWriter.Close()

        // Again calling Write method
        pipeWriter.Write([]byte("Author!"))
    }()

    // Defining data parameter of Read method
    data := make([]byte, 20)

    // Using for loop
    for i := 0; i < 3; i++ {

        // Calling pipeReader.Read() method
        n, err := pipeReader.Read(data)

        // If error is not nil panic
        if err != nil {
            panic(err)
        }

        // Prints the content read in buffer
        fmt.Printf("%s\n", data[:n])

        // Prints number of bytes read
        fmt.Printf("%v\n", n)
    }
}
```

**输出:**

```go
GfG
3
GeeksforGeeks
13
GfG is a CS-Portal.
19

```

这里，不返回错误，因为管道的写端直到“for”循环运行后才关闭。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.PipeReader.Read() function

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

    // Writing data to the pipe
    go func() {
        pipeWriter.Write([]byte("GfG"))
        pipeWriter.Write([]byte("GeeksforGeeks"))
        pipeWriter.Write([]byte("GfG is a CS-Portal."))

        // Closing write half of the pipe
        pipeWriter.Close()

        // Again calling Write method
        pipeWriter.Write([]byte("Author!"))
    }()

    // Defining data parameter of Read method
    data := make([]byte, 20)

    // Using for loop
    for i := 0; i < 4; i++ {

        // Calling pipeReader.Read() method
        n, err := pipeReader.Read(data)

        // If error is not nil panic
        if err != nil {
            panic(err)
        }

        // Prints the content read in buffer
        fmt.Printf("%s\n", data[:n])

        // Prints number of  bytes read
        fmt.Printf("%v\n", n)
    }
}
```

**输出:**

```go
GfG
3
GeeksforGeeks
13
GfG is a CS-Portal.
19
panic: EOF

goroutine 1 [running]:
main.main()
    /tmp/sandbox634835876/prog.go:43 +0x364

```

这里，当 for 循环第三次迭代后管道的写端关闭时，会返回一个 EOF 错误。