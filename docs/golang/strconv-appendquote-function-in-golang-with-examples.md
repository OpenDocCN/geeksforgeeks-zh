# Golang 中的

# strconv.AppendQuote（）函数及示例

> 原文： [https://www.geeksforgeeks.org/strconv-appendquote-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendquote-function-in-golang-with-examples/)

Go 语言提供内置支持，通过**strconv 包**实现与基本数据类型字符串表示的转换。该包提供了一个**AppendQuote（）函数**将表示 str 的双引号 Go 字符串文字（由 Quote 生成）附加到 num，并返回扩展缓冲区，如下语法所示。要访问 AppendQuote（）函数，您需要在程序中导入*strconv*包。

**语法：**

```go
func AppendQuote(num []byte, str string) []byte
```

**例 1:**

```go
// Golang program to illustrate
// strconv.AppendQuote() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendQuote() function
    val1 := []byte("Result 1: ")
    val1 = strconv.AppendQuote(val1,
         `"Welcome GeeksforGeeks"`)

    fmt.Println(string(val1))

    val2 := []byte("Result 2: ")
    val2 = strconv.AppendQuote(val2,
                          `"Hello"`)

    fmt.Println(string(val2))

}
```

**输出：**

```go
Result 1: "\"Welcome GeeksforGeeks\""
Result 2: "\"Hello\""

```

**例 2:**

```go
// Golang program to illustrate
// strconv.AppendQuote() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendQuote() function
    val1 := []byte("String 1: ")
    val1 = strconv.AppendQuote(val1,
                  `"GeeksforGeeks"`)

    fmt.Println(string(val1))
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("String 2: ")
    val2 = strconv.AppendQuote(val2, 
            `"Hello! How are you?"`)

    fmt.Println(string(val2))
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))

}
```

**输出：**

```go
String 1: "\"GeeksforGeeks\""
Length:  29
Capacity:  64
String 2: "\"Hello! How are you?\""
Length:  35
Capacity:  80

```