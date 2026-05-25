# Golang strconv.AppendQuoteRuneToASCII() 函数详解与示例

> Original: [https://www.geeksforgeeks.org/strconv-appendquoterunetoascii-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendquoterunetoascii-function-in-golang-with-examples/)

## 概述

Go 语言通过 `strconv` 包提供内置支持，实现基本数据类型的字符串表示形式之间的转换。此包提供 `AppendQuoteRuneToASCII()` 函数，用于将表示符文 `x` 的单引号 Go 字符文字（由 `QuoteRuneToASCII` 生成）附加到 `num` 并返回扩展缓冲区。

换句话说，`AppendQuoteRuneToASCII()` 函数用于将 Unicode 字符转换为由“单引号”产生的 ASCII 字符串，将结果追加到 `num` 的末尾，并返回追加的 `[]byte`。要访问 `AppendQuoteRuneToASCII()` 函数，您需要在程序中导入 `strconv` 包。

## 语法

```go
func AppendQuoteRuneToASCII(num []byte, x rune) []byte
```

这里，`num` 是 `[]byte`，`x` 是一个符文字面。`x` 的结果将附加到 `num` 的末尾。

## 示例 1

```go
// Golang program to illustrate the 
// strconv.AppendQuoteRuneToASCII() function
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Converting Unicode characters to 
    // ASCII strings resulting from "single quotes"
    // append the result to the end of the given []byte
    // Using AppendQuoteRuneToASCII() function
    val1 := []byte("Rune 1: ")
    val1 = strconv.AppendQuoteRuneToASCII(val1, 'B')
    fmt.Println(string(val1))

    val2 := []byte("Rune 2: ")
    val2 = strconv.AppendQuoteRuneToASCII(val2, '✈')
    fmt.Println(string(val2))
}
```

发帖主题：Re：Колибри0.7.8.0

## 示例 2

```go
// Golang program to illustrate the 
// strconv.AppendQuoteRuneToASCII() function
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Converting Unicode characters to ASCII
    // strings resulting from "single quotes"
    // append the result to the end of the given []byte
    // Using AppendQuoteRuneToASCII() function
    val1 := []byte("Rune 1: ")
    val1 = strconv.AppendQuoteRuneToASCII(val1, 'c')
    fmt.Println(string(val1))
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("Rune 2: ")
    val2 = strconv.AppendQuoteRuneToASCII(val2, '❄')
    fmt.Println(string(val2))
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))
}
```

发帖主题：Re：Колибри0.7.8.0