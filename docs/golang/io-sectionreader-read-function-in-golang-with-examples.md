# Golang 中的

# io.SectionReader.Read（）函数，示例为

> 原文： [https://www.geeksforgeeks.org/io-sectionreader-read-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-sectionreader-read-function-in-golang-with-examples/)

用围棋语言，*io*包为 I/O 原语提供基本接口。它的主要工作是封装这类原语之王正在进行的实现。Go 语言中的**SectionReader.Read（）**函数用于返回*NewSectionReader 读取的字节数*方法，该方法以缓冲区为参数，并且该函数是在 io 包下定义的，这里需要导入“io”包才能使用这些函数。

**语法：**

```go
func (s *SectionReader) Read(p []byte) (n int, err error)

```

这里，“s”是指向*NewSectionReader*方法返回的*SectionReader*的指针，“p”是指定字节长度的缓冲区。

**返回值：**返回指定长度的指定缓冲区返回内容的字节数，如果有则返回错误，如果没有错误则返回“nil”。

以下示例说明了上述方法的使用：

**例 1:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.Read() function

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
    reader := strings.NewReader("Geeks\n")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 2, 4)

    // Defining buffer using make keyword
    buf := make([]byte, 3)

    // Calling Read method with its parameter
    n, err := r.Read(buf)

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
Content in buffer: eks
n: 3

```

在上面的示例中，缓冲区的内容只有三个字节，因此返回“3”，并且在读取所述内容时没有抛出错误，因此错误为“nil”。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.Read() function

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
    reader := strings.NewReader("GeeksforGeeks\nis\na\nCS-Portal.")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 6, 34)

    // Defining buffer using make keyword
    buf := make([]byte, 25)

    // Calling Read method with its parameter
    n, err := r.Read(buf)

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
    /tmp/sandbox125171693/prog.go:31 +0x25a

```

这里，上面代码中使用的缓冲区中的内容的字节数比前面所述的要少，因此抛出 EOF 错误。