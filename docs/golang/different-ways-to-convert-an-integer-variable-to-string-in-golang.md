# 在 Golang 中将整数变量转换为字符串的不同方法

> 原文:[https://www . geeksforgeeks . org/different-way-to-convert-a-integer-variable-to-string-in-golang/](https://www.geeksforgeeks.org/different-ways-to-convert-an-integer-variable-to-string-in-golang/)

**整数**变量不能直接转换成**字符串**变量。为了在 Golang 中将字符串转换为整数类型，您需要将整数变量的值作为字符串存储在字符串变量中。为此，我们使用 **strconv 和 fmt** 包功能。

**1。伊藤()函数:****伊藤**代表整数到 ASCII，返回以 10 为基数的整数字符串表示。

**语法:**

```go
func Itoa(i int) string

```

**示例:** C 使用 strconv 将整数变量转换为字符串。Itoa()函数。

## Go

```go
// Go program to illustrate 
// How to convert integer 
// variable into String
package main

import (
    "fmt"
    "strconv"
)

//Main Function

func main() {
    i := 32
    s := strconv.Itoa(i)
    fmt.Printf("Type : %T \nValue : %v\n", s, s)

}
```