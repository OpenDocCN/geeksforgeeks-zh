# Golang 中的

# io.TeeReader（）函数，示例为

> 原文： [https://www.geeksforgeeks.org/io-teereader-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-teereader-function-in-golang-with-examples/)

用围棋语言，*io*包为 I/O 原语提供基本接口。它的主要工作是封装这类原语之王正在进行的实现。Go 语言中的**TeeReader（）**函数用于返回一个“Reader”，该“Reader”读取所述的“r”，然后将其写入所述的“w”. 这里，通过所述“r”执行的所有读取与对所述“w”的等效写入进行比较。此方法不需要任何内部缓冲，读取完成后即完成写入。此外，该函数是在 io 包下定义的。在这里，您需要导入“io”包才能使用这些函数。

**语法：**

```go
func TeeReader(r Reader, w Writer) Reader

```

这里，“r”是陈述的读者，“w”是陈述的作者。

**返回值：**返回一个“读卡器”，读取所述的“r”，然后将其写入给定的“w”。但是，写入内容时遇到的任何错误都将作为读取错误返回。

以下示例说明了上述方法的使用：

**例 1:**

```go
// Golang program to illustrate the usage of
// io.TeeReader() function

// Including main package
package main

// Importing fmt, io, strings, bytes, and os
import (
    "bytes"
    "fmt"
    "io"
    "os"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("GfG\n")

    // Defining buffer
    var buf bytes.Buffer

    // Calling TeeReader method with its parameters
    r := io.TeeReader(reader, &buf)

    // Calling Copy method with its parameters
    Reader, err := io.Copy(os.Stdout, r)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("n: %v\n", Reader)
}
```

**输出：**

```go
GfG
n: 4

```

在上面的示例中，使用 Copy（）方法返回“Reader”，使用字符串的 NewReader（）方法写入要读取的内容，这里还使用外部缓冲区。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.TeeReader() function

// Including main package
package main

// Importing fmt, io, strings, bytes, and os
import (
    "bytes"
    "fmt"
    "io"
    "os"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("GeeksforGeeks\nis\na\nCS-Portal.\n")

    // Defining buffer
    var buf bytes.Buffer

    // Calling TeeReader method with its parameters
    r := io.TeeReader(reader, &buf)

    // Calling Copy method with its parameters
    Reader, err := io.Copy(os.Stdout, r)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("n: %v\n", Reader)
}
```

**输出：**

```go
GeeksforGeeks
is
a
CS-Portal.
n: 30

```