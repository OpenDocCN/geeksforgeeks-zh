# Golang 中的

# io.SectionReader.Size（）函数及示例

> 原文： [https://www.geeksforgeeks.org/io-sectionreader-size-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-sectionreader-size-function-in-golang-with-examples/)

用围棋语言，*io*包为 I/O 原语提供基本接口。它的主要工作是封装这类原语之王正在进行的实现。Go 语言中的**SectionReader.Size（）**函数用于查找*NewSectionReader（）返回的节的大小*方法，以字节为单位。此外，该函数是在 io 包下定义的。在这里，您需要导入“io”包才能使用这些函数。

**语法：**

```go
func (s *SectionReader) Size() int64

```

这里，“s”是指向*NewSectionReader*方法返回的*SectionReader*的指针。

**返回值：**返回返回的节的大小，以字节为单位，类型为 int64。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.Size() function

// Including the main package
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

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 1, 4)

    // Calling Size method
    size := r.Size()

    // Prints output
    fmt.Printf("The size of the section in bytes is: %v\n", size)
}
```

**输出：**

```go
The size of the section in bytes is: 4

```

**例 2:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.Size() function

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
    reader := strings.NewReader("GeeksforGeeks\nis\na\nCS-Portal.\n")

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 5, 23)

    // Calling Size method
    size := r.Size()

    // Prints output
    fmt.Printf("The size of the section in bytes is: %v\n", size)
}
```

**输出：**

```go
The size of the section in bytes is: 23

```