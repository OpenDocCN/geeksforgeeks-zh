# 如何使用 strconv。Golang 中的 QuoteRune()函数？

> 原文:[https://www . geeksforgeeks . org/how-用法-strconv-quote rune-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-quoterune-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **QuoteRune()函数**，用来查找一个单引号的代表符文的 Go 字符串文字，返回的字符串使用 Go 转义序列(\t，\n，\xFF，\u0100)来控制由 IsPrint 定义的字符和不可打印的字符。要访问 QuoteRune()函数，您需要在程序中导入 **strconv 包**。

**语法:**

```go
func QuoteRune(rn rune) string
```

**参数:**该函数取符文类型的一个参数，即 rn。

**返回值:**这个函数返回一个单引号的 Go 字符串，代表符文。

**例 1:**

```go
// Golang program to illustrate 
// strconv.QuoteRune() Function
package main

import (
    "fmt"
    "strconv"
)

func main() { 

    // Finding a single-quoted Go 
    // string literal representing rune
    // Using QuoteRune() function
    r := strconv.QuoteRune('♥')
    fmt.Println(r)

}

```

**输出:**

```go
'♥'
```

**例 2:**

```go
// Golang program to illustrate
// strconv.QuoteRune() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a single-quoted Go 
    // string literal representing rune
    // Using QuoteRune() function
    val1 := strconv.QuoteRune('♣')
    fmt.Println("Result 1: ", val1)
    fmt.Println("Length 1: ", len(val1))

    val2 := strconv.QuoteRune('→')
    fmt.Println("Result 2: ", val2)
    fmt.Println("Length 2: ", len(val2))

}

```

**输出:**

```go
Result 1:  '♣'
Length 1:  5
Result 2:  '→'
Length 2:  5

```