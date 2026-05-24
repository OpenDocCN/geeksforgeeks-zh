# Golang 中的

# io.SectionReader.Seek（）函数及示例

> 原文： [https://www.geeksforgeeks.org/io-sectionreader-seek-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-sectionreader-seek-function-in-golang-with-examples/)

用围棋语言，*io*包为 I/O 原语提供基本接口。它的主要工作是封装这种原语之王的持续实现。**SectionReader.Seek（）Go 语言中的**函数用于在所述偏移量和位置的帮助下查找新的偏移量。此外，该函数在 io 包下定义。在这里，您需要导入“io”包才能使用这些函数。

**语法：**

```go
func (s *SectionReader) Seek(offset int64, whence int) (int64, error)

```

这里，“s”是指向*NewSectionReader*方法返回的*SectionReader*的指针，“offset”是 int64 类型，“whence”是 int 类型。

**返回值：**根据给定的偏移量加上 whence 返回一个新的偏移量，如果有错误也返回一个错误。

**注：**Seek*从*处有三个常量值，如下所示：

*   SeekStart=0，它相对于所述文件的开头进行查找。
*   SeekCurrent=1，它相对于所述文件的最新偏移量进行查找。
*   SeekEnd=2，它相对于所述文件的结尾进行查找。

**例 1:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.Seek() function

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

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 1, 4)

    // Calling Seek method with its parameters
    Newoffset, err := r.Seek(6, 1)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("The new offset is: %v\n", Newoffset)
}
```

**输出：**

```go
The new offset is: 6

```

在上面的示例中，Seek whence 的值为 1，这意味着它是“SeekCurrent”，因此它相对于当前偏移进行搜索。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.SectionReader.Seek() function

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

    // Calling NewSectionReader method with its parameters
    r := io.NewSectionReader(reader, 1, 4)

    // Calling Seek method with its parameters
    Newoffset, err := r.Seek(6, io.SeekEnd)

    // If error is not nil then panics
    if err != nil {
        panic(err)
    }

    // Prints output
    fmt.Printf("The new offset is: %v\n", Newoffset)
}
```

**输出：**

```go
The new offset is: 10

```

在这里，Seek 的值是“SeekEnd”，意思是相对于终点进行搜索。