# io。用例子读取 Golang 中的至少()函数

> 原文:[https://www . geesforgeks . org/io-read 至少-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-readatleast-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的**read 至少()**函数用于从所述读取器“r”读取到所述缓冲器“buf”中，直到它已经读取了至少所述最小数量的字节。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func ReadAtLeast(r Reader, buf []byte, min int) (n int, err error)

```

这里，“r”是读取器声明的，“buf”是缓冲器声明的，“min”是读取器读取给定缓冲器之前的最小字节数。

**返回值:**返回所述缓冲区复制的字节数，如果读取的字节数小于最小字节数，则返回错误。这里，当且仅当错误为零时，返回的“n”将大于“min”字节。但是，当且仅当没有读取字节时，返回的错误是“EOF”。

**注意:**如果在读取的字节数少于规定的“最小”字节数后发生电渗流，则该方法返回*意外电渗流*错误。但是，如果所述最小字节数大于所述缓冲区的长度，则该方法返回 *ErrShortBuffer* 错误。然而，如果所述读取器在读取至少所述最小字节后返回错误，则该错误被拒绝。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.ReadAtLeast() function

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

    // Calling ReadAtLeast method with its parameters
    n, err := io.ReadAtLeast(reader, buffer, 3)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Number of bytes in the buffer: %d\n", n)
    fmt.Printf("Content in buffer: %s\n", buffer)
}
```

**输出:**

```go
Number of bytes in the buffer: 5
Content in buffer: Geeks

```

这里，返回的“n”即 5 大于“min”即 3，因为误差为零。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.ReadAtLeast() function

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
    reader := strings.NewReader("GeeksforGeeks")

    // Defining buffer of specified length
    // using make keyword
    buffer := make([]byte, 4)

    // Calling ReadAtLeast method with its parameters
    n, err := io.ReadAtLeast(reader, buffer, 5)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Number of bytes in the buffer: %d\n", n)
    fmt.Printf("Content in buffer: %s\n", buffer)
}
```

**输出:**

```go
panic: short buffer

goroutine 1 [running]:
main.main()
    /tmp/sandbox041442440/prog.go:29 +0x20f

```

这里，上述代码中所述的缓冲区的长度小于所述的“最小”字节，因此会引发错误。