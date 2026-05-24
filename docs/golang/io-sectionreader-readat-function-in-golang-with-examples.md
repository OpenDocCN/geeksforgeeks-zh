# Golang 中的

# io.SectionReader.ReadAt（）函数，示例为

> 原文： [https://www.geeksforgeeks.org/io-sectionreader-readat-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-sectionreader-readat-function-in-golang-with-examples/)

用围棋语言，*io*包为 I/O 原语提供基本接口。它的主要工作是封装这类原语之王正在进行的实现。Go 语言中的**SectionReader.ReadAt（）**函数用于返回*NewSectionReader 读取的字节数*方法，该方法以缓冲区和偏移量为参数，并且该函数在 io 包下定义，这里需要导入“io”包才能使用这些函数。

**语法：**

```go
func (s *SectionReader) ReadAt(p []byte, off int64) (n int, err error)

```

这里，“s”是指向*NewSectionReader*方法返回的*SectionReader*的指针，“p”是规定字节长度的缓冲区，“off”是从读取开始的 int64 类型的偏移量。

**返回值：**返回指定长度的指定缓冲区返回的内容字节数以及偏移量，如果有错误也返回错误，如果没有错误则返回“nil”。

以下示例说明了上述方法的使用：

**例 1:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.ReadAt() function

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
    reader := strings.NewReader("GeeksforGeeks\n")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 6, 12)

    // Defining buffer using make keyword
    buf := make([]byte, 4)

    // Calling ReadAt method with its parameters
    n, err := r.ReadAt(buf, 2)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Content in buffer: %s\n", buf)
    fmt.Printf("n: %v\n", n)
}
```

**输出：**

```go
Content in buffer: Geek
n: 4

```

在上面的示例中，首先从 NewSectionReader（）返回内容，然后在 ReadAt（）方法中从给定的偏移量读取内容，直到缓冲区中指定的字节数为止。然后返回结果内容的字节数作为此处的输出。此外，上面缓冲区的内容只有 4 个字节，因此返回“4”，并且在读取所述内容时没有抛出错误，因此错误为“nil”。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.ReadAt() function

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
    reader := strings.NewReader("Computer Science!")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 6, 12)

    // Defining buffer using make keyword
    buf := make([]byte, 10)

    // Calling ReadAt method with its parameters
    n, err := r.ReadAt(buf, 2)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("Content in buffer: %s\n", buf)
    fmt.Printf("n: %v\n", n)
}
```

**输出：**

```go
panic: EOF

goroutine 1 [running]:
main.main()
    /tmp/sandbox798260752/prog.go:31 +0x263

```

这里，上面代码中使用的缓冲区中的内容的字节数比前面所述的要少，因此会抛出 EOF 错误。