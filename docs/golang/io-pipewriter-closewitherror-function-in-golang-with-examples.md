# io。在 Golang 中使用函数 CloseWithError()并举例

> 原文:[https://www . geesforgeks . org/io-pipe writer-closewithror-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-pipewriter-closewitherror-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。**管道工。Go 语言中的 CloseWithError()** 函数用于关闭编写器。但是，从*管道头*连续读取，即读取管道的一半不会返回任何字节，如果错误为零，则返回错误*错误*或 EOF 错误。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func (w *PipeWriter) CloseWithError(err error) error

```

这里，“w”是指向 PipeWriter 的指针。其中 PipeWriter 是管道的写半部分，“err”是我们在代码中声明的错误，如果出现错误，将打印代码。

**返回值:**如我们所述，它返回一个错误，否则如果错误为零，它返回一个电渗流。

**注意:**如果前一个错误存在，该方法从不重写前一个错误，并且每次都返回“nil”。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.PipeWriter.CloseWithError() function

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

        // Calling CloseWithError() method with
        // its parameter
        pipeReader.CloseWithError(fmt.Errorf("There is an "+
                              "error in the code written!"))
    }()

    // Using for loop
    for i := 0; i < 1; i++ {

        // Calling pipeWriter.Write() method
        n, err := pipeWriter.Write([]byte("GeeksforGeeks!"))

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
GeeksforGeeks!
14

```

这里不返回任何错误，因为这里没有调用 CloseWithError()方法，因为循环仅在一次读取操作后停止。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.PipeWriter.CloseWithError() function

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

        // Calling CloseWithError() method with
        // its parameter
        pipeReader.CloseWithError(fmt.Errorf("There is"+
                      " an error in the code written!"))
    }()

    // Using for loop
    for i := 0; i < 2; i++ {

        // Calling pipeWriter.Write() method
        n, err := pipeWriter.Write([]byte("GeeksforGeeks!"))

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
GeeksforGeeks!
14
panic: There is an error in the code written!

goroutine 1 [running]:
main.main()
    /tmp/sandbox246824679/prog.go:39 +0x3c2

```

这里，调用 CloseWithError()方法时会引发一个错误，因为“for”循环在第二次迭代后停止。这里返回的错误如我们所述。