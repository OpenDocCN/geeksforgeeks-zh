# Golang 中的 io.SectionReader.Seek() 函数及示例

> 原文： [https://www.geeksforgeeks.org/io-sectionreader-seek-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-sectionreader-seek-function-in-golang-with-examples/)

在 Go 语言中，`io` 包为 I/O 原语提供基本接口。它的主要工作是封装底层实现。`SectionReader.Seek()` 函数用于根据给定的偏移量和位置查找新的偏移量。该函数在 `io` 包下定义，需要导入 `"io"` 包才能使用。

## 语法

```go
func (s *SectionReader) Seek(offset int64, whence int) (int64, error)
```

这里，`s` 是指向由 `NewSectionReader` 方法返回的 `SectionReader` 的指针，`offset` 是 `int64` 类型，`whence` 是 `int` 类型。

## 返回值

根据给定的偏移量加上 `whence` 返回一个新的偏移量，如果有错误也返回一个错误。

## 注：Seek whence 常量

`Seek` 的 `whence` 参数有三个常量值：

*   `SeekStart=0`：相对于文件的开头进行查找。
*   `SeekCurrent=1`：相对于文件的当前偏移量进行查找。
*   `SeekEnd=2`：相对于文件的结尾进行查找。

## 例 1

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

在上面的示例中，`Seek` 的 `whence` 值为 `1`，即 `SeekCurrent`，因此它相对于当前偏移进行查找。

## 例 2

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

在这里，`Seek` 的 `whence` 值是 `io.SeekEnd`，意思是相对于文件结尾进行查找。