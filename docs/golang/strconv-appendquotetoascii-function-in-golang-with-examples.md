# Golang 中的 strcom.AppendQuoteToASCII()函数，示例为

> Original: [https://www.geeksforgeeks.org/strconv-appendquotetoascii-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendquotetoascii-function-in-golang-with-examples/)

Go 语言提供内置支持，通过 strconv 包实现基本数据类型的字符串表示形式之间的转换。 此包提供了一个**AppendQuoteToASCII()函数**，用于将由 QuoteToASCII 生成的表示字符串的双引号 GO 字符串文字附加到 num 并返回扩展缓冲区。 或者换句话说，将字符串 str 转换为由“双引号”产生的 ASCII 字符串，将结果附加到 num 的末尾并返回附加的[]字节。 要访问 AppendQuoteToASCII()函数，您需要在程序中导入 strconv 包。

**语法：**

```go
func AppendQuoteToASCII(num []byte, str string) []byte
```

这里，num 是[]字节，str 是字符串。 Str 的结果将追加到 num 的末尾。

**示例 1：**

```go
// Golang program to illustrate the
// strconv.AppendQuoteToASCII() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Converting the string to ASCII
    // strings resulting from "single quotes"
    // append the result to the
    // end of the given []byte
    // Using AppendQuoteToASCII() function
    val1 := []byte("Result 1: ")
    val1 = strconv.AppendQuoteToASCII(val1,
                  `"Hello! GeeksforGeeks"`)
    fmt.Println(string(val1))

    val2 := []byte("Result 2: ")
    val2 = strconv.AppendQuoteToASCII(val2, `"Hey"`)
    fmt.Println(string(val2))

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: "\"Hello! GeeksforGeeks\""
Result 2: "\"Hey\""

```

**示例 2：**

```go
// Golang program to illustrate the
// strconv.AppendQuoteToASCII() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Converting the string to ASCII 
    // strings resulting from "single quotes"
    // append the result to the 
    // end of the given []byte
    // Using AppendQuoteToASCII() function
    val1 := []byte("Result 1: ")
    val1 = strconv.AppendQuoteToASCII(val1,
                             `"Hello! GFG"`)
    fmt.Println(string(val1))
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("Result 2: ")
    val2 = strconv.AppendQuoteToASCII(val2, `"Welcome"`)
    fmt.Println(string(val2))
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: "\"Hello! GFG\""
Length:  26
Capacity:  48
Result 2: "\"Welcome\""
Length:  23
Capacity:  48

```