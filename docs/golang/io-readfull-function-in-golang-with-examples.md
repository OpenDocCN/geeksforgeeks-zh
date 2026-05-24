# Golang 中的

# io.ReadFull（）函数，示例为

> 原文： [https://www.geeksforgeeks.org/io-readfull-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-readfull-function-in-golang-with-examples/)

用围棋语言，*io*包为 I/O 原语提供基本接口。它的主要工作是封装这类原语之王正在进行的实现。Go 语言中的**ReadFull（）**函数用于从指定的读取器“r”读入指定的缓冲区“buf”复制的字节数正好等于指定缓冲区的长度。此外，该函数是在 io 包下定义的。在这里，您需要导入“io”包才能使用这些函数。

**语法：**

```go
func ReadFull(r Reader, buf []byte) (n int, err error)

```

这里，“r”表示读卡器，“buf”表示指定长度的缓冲区。

**返回值：**返回指定缓冲区复制的字节数，如果读取的字节数小于指定缓冲区的长度，则返回一个错误。这里，当且仅当错误为零时，返回的“n”将等于指定缓冲区的长度。但是，返回的错误为“EOF”当且仅当未读取字节时。

**注意：**如果在读取较少字节（而不是所有字节）后发生 EOF，则此方法返回*错误*错误除外。但是，如果所述读卡器在读取至少一段缓冲区后返回错误，则错误被拒绝。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.ReadFull() function

// Including main package
package main

// Importing fmt, io, and strings
import (
    "fmt"
    "io"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("Geeks")

    // Defining buffer of specified length
    // using make keyword
    buffer := make([]byte, 4)

    // Calling ReadFull method with its parameters
    n, err := io.ReadFull(reader, buffer)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Number of bytes in the buffer: %d\n", n)
    fmt.Printf("Content in buffer: %s\n", buffer)
}
```

**输出：**

```go
Number of bytes in the buffer: 4
Content in buffer: Geek

```

这里，返回的'n'即 4 等于'buf'的长度，因为错误为零。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.ReadFull() function

// Including main package
package main

// Importing fmt, io, and strings
import (
    "fmt"
    "io"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("Geeks")

    // Defining buffer of specified length
    // using make keyword
    buffer := make([]byte, 6)

    // Calling ReadFull method with its parameters
    n, err := io.ReadFull(reader, buffer)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Number of bytes in the buffer: %d\n", n)
    fmt.Printf("Content in buffer: %s\n", buffer)
}
```

**输出：**

```go
panic: unexpected EOF

goroutine 1 [running]:
main.main()
    /tmp/sandbox503804944/prog.go:29 +0x210

```

这里，上面代码中所述的缓冲区的长度大于从读取器读取的字节，因此引发 EOF 错误。