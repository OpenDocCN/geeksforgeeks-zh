# 如何使用 strconv。Golang 中的 Quote()函数？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-quote-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-quote-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **Quote()函数**，用来查找一个表示 str 的双引号 Go 字符串文字，返回的字符串使用 Go 转义序列(\t，\n，\xFF，\u0100)来控制由 IsPrint 定义的字符和不可打印字符。要访问 Quote()函数，您需要在程序中导入 strconv 包。

**语法:**

```go
func Quote(str string) string
```

**参数:**该函数取一个字符串类型的参数，即 str。

**返回值:**这个函数返回一个双引号的 Go 字符串，代表字符串。

**例 1:**

```go
// Golang program to illustrate strconv.Quote() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Finding a double-quoted Go
    // string literal representing str
    // Using Quote() function
    str := strconv.Quote(`" Hello 
     Welcome to GeeksforGeeks "`)
    fmt.Println(str)

}
```

**输出:**

```go
"\" Hello \n     Welcome to GeeksforGeeks \""
```

**例 2:**

```go
// Golang program to illustrate
// strconv.Quote() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a double-quoted Go string literal
    // Using Quote() function
    val1 := strconv.Quote(`"Hello! GFG   "`)
    fmt.Println("Result 1: ", val1)
    fmt.Println("Length 1: ", len(val1))

    val2 := strconv.Quote(`"Welcome!
        GeeksforGeeks"`)
    fmt.Println("Result 2: ", val2)
    fmt.Println("Length 2: ", len(val2))

}
```

**输出:**

```go
Result 1:  "\"Hello! GFG   \""
Length 1:  19
Result 2:  "\"Welcome!\n        GeeksforGeeks\""
Length 2:  37

```