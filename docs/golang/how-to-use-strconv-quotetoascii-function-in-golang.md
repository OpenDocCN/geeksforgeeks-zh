# 如何使用 strconv。Golang 中的 QuoteToASCII()函数？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-quote ascii-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-quotetoascii-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个**quote ASCII()函数**，用来查找一个表示 str 的双引号 Go 字符串，返回的字符串使用 Go 转义序列(\t，\n，\xFF，\u0100)来表示非 ASCII 字符和由 IsPrint 定义的不可打印字符。要访问 QuoteToASCII()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
 func QuoteToASCII(str string) string
```

**参数:**该函数取一个字符串类型的参数，即 str。

**返回值:**这个函数返回一个双引号的 Go 字符串文字，代表字符串。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// strconv.QuoteToASCII() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a double-quoted Go 
    // string literal representing str
    // Using QuoteToASCII() function
    str := strconv.QuoteToASCII(`"♥ Welcome GeeksforGeeks ♥ "`)
    fmt.Println (str)    
}

```

**输出:**

```go
"\"\u2665 Welcome GeeksforGeeks \u2665 \""
```

**例 2:**

```go
// Golang program to illustrate 
// strconv.QuoteToASCII() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a double-quoted Go 
    // string literal representing rune
    // Using QuoteToASCII() function
    val1 := strconv.QuoteToASCII(`"I like Δ "`)
    fmt.Println("Result 1: ", val1)
    fmt.Println("Length 1: ", len(val1))

    val2 := strconv.QuoteToASCII(`"I love     ♦"`)
    fmt.Println("Result 2: ", val2)
    fmt.Println("Length 2: ", len(val2)) 
}

```

**输出:**

```go
Result 1:  "\"I like \u0394\t\""
Length 1:  21
Result 2:  "\"I love     \u2666\""
Length 2:  23

```