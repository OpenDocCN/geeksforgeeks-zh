# io。Golang 中的 MultiReader()函数及示例

> 原文:[https://www . geesforgeks . org/io-multi-reader-function-in-golang-with-examples/](https://www.geeksforgeeks.org/io-multireader-function-in-golang-with-examples/)

在 Go 语言中， *io* 包为输入/输出原语提供基本接口。它的主要工作是封装这种原语之王正在进行的实现。Go 语言中的 **MultiReader()** 函数用于返回一个“Reader”，它是所有指定输入读取器的逻辑连接。然而，这些陈述的读者是按顺序阅读的。在所有规定的输入都返回一个电渗流后，即文件结束时，“读取”将返回一个电渗流。此外，该功能在 io 包中定义。在这里，您需要导入“io”包才能使用这些功能。

**语法:**

```go
func MultiReader(readers ...Reader) Reader

```

在这里，“读者”是所述读者的数量。

**返回值:**它返回一个“Reader”，它是所有给定输入读取器的逻辑串联。如果任何一个声明的读取器返回一个非零错误或非电渗流错误，那么“读取”将返回该错误。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang program to illustrate the usage of
// io.MultiReader() function

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

    // Defining readers using NewReader method
    reader1 := strings.NewReader("Geeks\n")
    reader2 := strings.NewReader("GfG\n")
    reader3 := strings.NewReader("CS\n")

    // Calling MultiReader method with its parameters
    r := io.MultiReader(reader1, reader2, reader3)

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
Geeks
GfG
CS
n: 13

```

在上面的示例中，使用了 Copy()方法来返回所有串联读取器的结果，并从写入要读取的内容的位置使用了字符串的 NewReader()方法。

**例 2:**

```go
// Golang program to illustrate the usage of
// io.MultiReader() function

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

    // Defining readers using NewReader method
    reader1 := strings.NewReader("104\n")
    reader2 := strings.NewReader("33.3\n")
    reader3 := strings.NewReader("703243242\n")

    // Calling MultiReader method with its parameters
    r := io.MultiReader(reader1, reader2, reader3)

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
104
33.3
703243242
n: 19

```