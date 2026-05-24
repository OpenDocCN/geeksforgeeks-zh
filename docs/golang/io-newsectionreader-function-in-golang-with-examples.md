# io。Golang 中的 NewSectionReader()函数及示例

> 原文:[https://www . geesforgeks . org/io-newsectionreader-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-newsectionreader-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的 **NewSectionReader()** 函数用于返回一个 *SectionReader* ，该函数从指定的 reader“r”开始读取，从指定的偏移量“off”开始，以 EOF 结束，即给定“n”字节数后的文件结束。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func NewSectionReader(r ReaderAt, off int64, n int64) *SectionReader

```

这里，“r”是从哪里读取内容的读取器，“off”是从哪里开始读取内容的规定偏移量，“n”是读取内容之前的字节数。

**返回值:**它返回一个“SectionReader”，从指定的读取器“r”读取，该读取器从指定的偏移量“off”开始，以 EOF 结束，即在给定的“n”字节数后的文件结束。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang program to illustrate the usage of
// io.NewSectionReader() function

// Including main package
package main

// Importing fmt, io, strings, and os
import (
    "fmt"
    "io"
    "os"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("Geeks\n")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 3, 5)

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

**输出:**

```go
ks
n: 3

```

在上面的示例中，使用 Copy()方法来返回输出，并从写入要读取的内容的位置使用字符串的 NewReader()方法。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.NewSectionReader() function

// Including main package
package main

// Importing fmt, io, strings, and os
import (
    "fmt"
    "io"
    "os"
    "strings"
)

// Calling main
func main() {

    // Defining reader using NewReader method
    reader := strings.NewReader("GeeksforGeeks\nis\na\nCS-Portal.\n")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 7, 40)

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

**输出:**

```go
rGeeks
is
a
CS-Portal.
n: 23

```

这里，内容从偏移量“7”开始，在字节数达到“40”后终止。但是在这里返回的输出中，复制的内容是“23”字节，所以“n”是 23。