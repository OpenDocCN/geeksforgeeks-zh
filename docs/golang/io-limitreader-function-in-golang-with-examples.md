# io。Golang 中的 LimitReader()函数示例

> 原文:[https://www . geesforgeks . org/io-limitereader-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-limitreader-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的**limitereader()**函数用于返回一个“Reader”，它从所述的“r”中读取，但是如果在读取了所述的“n”字节数之后达到了 EOF，即文件的结尾，它就会暂停。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func LimitReader(r Reader, n int64) Reader

```

这里，“r”是所述的读取器，“n”是字节数。

**返回值:**它返回一个从所述“r”读取的读取器。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang program to illustrate the usage of
// io.LimitReader() function

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

    // Defining r using NewReader
    r := strings.NewReader("Geeks\n")

    // Calling LimitReader method with its parameters
    res := io.LimitReader(r, 3)

    // Calling Copy method with its parameters
    op, err := io.Copy(os.Stdout, res)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("\nn: %v\n", op)
}
```

**输出:**

```go
Gee
n: 3

```

在上面的示例中，使用 Copy()方法返回“Reader”，使用 NewReader()方法从写入要读取的内容的位置读取字符串。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.LimitReader() function

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

    // Defining r using NewReader
    r := strings.NewReader("GfG\nis\na\nCS-Portal.\n")

    // Calling LimitReader method with its parameters
    res := io.LimitReader(r, 8)

    // Calling Copy method with its parameters
    op, err := io.Copy(os.Stdout, res)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("\nn: %v\n", op)
}
```

**输出:**

```go
GfG
is
a
n: 8

```