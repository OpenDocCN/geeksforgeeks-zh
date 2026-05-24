# io。用例子复制 Golang 中的()函数

> 原文:[https://www . geesforgeks . org/io-copy-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-copy-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的 **Copy()** 功能用于从指定的 src(即源)复制到 *dst(即目标)，直到在 src 上达到 EOF(即文件结束)或抛出错误。这里，当 *src* 由 *WriterTo* 接口实现时，则通过对 src 的调用来实现副本。WriteTo(dst)。否则，如果 dst 是由 *ReaderFrom* 接口实现的，那么副本是通过对 dst 的调用来实现的。读取自(src)。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。*

**语法:**

```go
func Copy(dst Writer, src Reader) (written int64, err error)

```

这里，“dst”是目的地，“src”是内容被复制到目的地的来源。
**返回值:**返回拷贝到“dst”的 int64 类型的字节总数，还返回从 src 拷贝到 dst 时遇到的第一个错误(如果有)。如果复制没有错误，则返回“无”。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang program to illustrate the usage of
// io.Copy() function

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
    src := strings.NewReader("GeeksforGeeks\n")

    // Defining destination using Stdout
    dst := os.Stdout

    // Calling Copy method with its parameters
    bytes, err := io.Copy(dst, src)

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
GeeksforGeeks
The number of bytes are: 14

```

**例 2:**

```go
// Golang program to illustrate the usage of
// io.Copy() function

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
    src := strings.NewReader("Nidhi: F\nRahul: M\nNisha: F\n")

    // Defining destination using Stdout
    dst := os.Stdout

    // Calling Copy method with its parameters
    bytes, err := io.Copy(dst, src)

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
Nidhi: F
Rahul: M
Nisha: F
The number of bytes are: 27

```

这里，在上面的例子中，使用了 NewReader()方法，从这里读取要复制的内容。这里使用“Stdout”来创建一个默认的文件描述符，复制的内容将被写入其中。