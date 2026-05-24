# 如何使用 strconv。Golang 中的 QuoteRuneToGraphic()函数？

> 原文:[https://www . geeksforgeeks . org/how-用法-strconv-quoterunegracic-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-quoterunetographic-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个**引用文字()函数**，用来找到一个代表符文的单引号围棋字符。如果符文不是 IsGraphic 定义的 Unicode 图形字符，则返回的字符串将使用 Go 转义序列(\t，\n，\xFF，\u0100)。要访问**quoteronegracic()功能**，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func QuoteRuneToGraphic(rn rune) string
```

**参数:**该函数取符文类型的一个参数，即 rn。

**返回值:**这个函数返回一个单引号的 Go 字符串，代表符文。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate 
// strconv.QuoteRuneToGraphic() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a single-quoted Go
    // string literal representing rune
    // Using func QuoteRuneToGraphic() function
    str := strconv.QuoteRuneToGraphic('♥')
    fmt.Println (str)

}

```

**输出:**

```go
'♥'
```

**例 2:**

```go
// Golang program to illustrate 
// strconv.QuoteRuneToGraphic() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a single-quoted Go 
    // string literal representing rune
    // Using QuoteRuneToGraphic() function
    val1 := strconv.QuoteRuneToGraphic('®')
    fmt.Println("Result 1: ", val1)

    val2 := strconv.QuoteRuneToGraphic('\u2666')
    fmt.Println("Result 2: ", val2)

     val3 := strconv.QuoteRuneToGraphic('\u000a')
    fmt.Println("Result 3: ", val3) 
}

```

**输出:**

```go
Result 1:  '®'
Result 2:  '♦'
Result 3:  '\n'

```