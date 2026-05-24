# 如何使用 strconv。QuoteRuneToASCII()函数在 Golang？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-quoterunetoasci-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-quoterunetoascii-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个**quoternetoascii()函数**，用来查找一个代表符文的单引号 Go 字符串文字，返回的字符串使用 Go 转义序列(\t，\n，\xFF，\u0100)来表示非 ASCII 字符和由 IsPrint 定义的不可打印字符。要访问 QuoteRuneToASCII()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func QuoteRuneToASCII(rn rune) string
```

**参数:**该函数取符文类型的一个参数，即 rn。

**返回值:**这个函数返回一个单引号的 Go 字符串，代表符文。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate 
// strconv.QuoteRuneToASCII() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a single-quoted Go 
    // string literal representing rune
    // Using QuoteRuneToASCII() function
    r := strconv.QuoteRuneToASCII('♥')
    fmt.Println (r)

}

```

**输出:**

```go
'\u2665'
```

**例 2:**

```go
// Golang program to illustrate 
// strconv.QuoteRuneToASCII() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a single-quoted Go 
    // string literal representing rune
    // Using QuoteRuneToASCII() function
    val1 := strconv.QuoteRuneToASCII('♣')
    fmt.Println("Result 1: ", val1)
    fmt.Println("Length 1: ", len(val1))

    val2 := strconv.QuoteRuneToASCII('→')
    fmt.Println("Result 2: ", val2)
    fmt.Println("Length 2: ", len(val2))

}

```

**输出:**

```go
Result 1:  '\u2663'
Length 1:  8
Result 2:  '\u2192'
Length 2:  8

```