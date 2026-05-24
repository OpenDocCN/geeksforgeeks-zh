# 如何使用 strconv。Golang 中的 QuoteToGraphic()函数？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-quote tographic-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-quotetographic-function-in-golang/)

Go 语言提供了内置的支持，通过 strconv Package 实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **QuoteToGraphic()函数**，用来查找一个表示 str 的双引号 Go 字符串文字，返回的字符串保持 IsGraphic 定义的 Unicode 图形字符不变，对非图形字符使用 Go 转义序列(\t，\n，\xFF，\u0100)。要访问 QuoteToGraphic()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func QuoteToGraphic(str string) string
```

**参数:**该函数取一个字符串类型的参数，即 str。

**返回值:**这个函数返回一个双引号的 Go 字符串文字，代表字符串。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate 
// strconv.QuoteToGraphic() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a double-quoted Go 
    // string literal representing str
    // Using func QuoteToGraphic() function
    str := strconv.QuoteToGraphic("\u2665 Welcome GeeksforGeeks \u2665")
    fmt.Println (str)

}

```

**输出:**

```go
"♥ Welcome GeeksforGeeks ♥"
```

**例 2:**

```go
// Golang program to illustrate
// strconv.QuoteToGraphic() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a double-quoted Go 
    // string literal representing rune
    // Using QuoteToGraphic() function
    val1 := strconv.QuoteToGraphic(`"I like Δ    "`)
    fmt.Println("Result 1: ", val1)
    fmt.Println("Length 1: ", len(val1))

    val2 := strconv.QuoteToGraphic("I love \u2666")
    fmt.Println("Result 2: ", val2)
    fmt.Println("Length 2: ", len(val2))
}

```

**输出:**

```go
Result 1:  "\"I like Δ\t\""
Length 1:  17
Result 2:  "I love ♦"
Length 2:  12

```