# Golang 中的

# strconv.AppendQuoteRune（）函数与示例

> 原文： [https://www.geeksforgeeks.org/strconv-appendquoterune-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendquoterune-function-in-golang-with-examples/)

Go 语言提供了内置支持，在**strconv 包**的帮助下，实现基本数据类型的字符串表示之间的转换。该包提供了一个**AppendQuoteRune（）函数**在 num 后面附加一个单引号 Go 字符，表示由 QuoteRune 生成的符文 x，并返回扩展缓冲区，如下语法所示。要访问 AppendQuoteRune（）函数，需要在程序中导入 strconv 包。

**语法：**

```go
func AppendQuoteRune(num []byte, x rune) []byte
```

**例 1:**

```go
// Golang program to illustrate
// strconv.AppendQuoteRune() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendQuoteRune() function
    val1 := []byte("Rune 1: ")
    val1 = strconv.AppendQuoteRune(val1, 'B')
    fmt.Println(string(val1))

    val2 := []byte("Rune 2: ")
    val2 = strconv.AppendQuoteRune(val2, '\a')
    fmt.Println(string(val2))

}
```

**输出：**

```go
Rune 1: 'B'
Rune 2: '\a'

```

**例 2:**

```
// Golang program to illustrate
// strconv.AppendQuoteRune() Function

package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendQuoteRune() function
    val1 := []byte("Rune 1: ")
    val1 = strconv.AppendQuoteRune(val1, 'c')
    fmt.Println(string(val1))
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("Rune 2: ")
    val2 = strconv.AppendQuoteRune(val2, '💣')
    fmt.Println(string(val2))
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))

}

```go

**输出：**

```
Rune 1: 'c'
Length:  11
Capacity:  16
Rune 2: '💣'
Length:  14
Capacity:  16

```