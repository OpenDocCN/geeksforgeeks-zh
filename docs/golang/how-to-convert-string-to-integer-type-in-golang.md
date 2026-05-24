# 如何在 Golang 中将字符串转换为整数类型？

> 原文:[https://www . geesforgeks . org/如何将字符串转换为整数类型 in-golang/](https://www.geeksforgeeks.org/how-to-convert-string-to-integer-type-in-golang/)

[**Golang 中的字符串**](https://www.geeksforgeeks.org/strings-in-golang/) 是一个可变宽度字符序列，其中每个字符都由一个或多个使用 UTF-8 编码的字节表示。在 Go 语言中，有符号和无符号整数都有四种不同的大小。为了在 Golang 中将字符串转换为整数类型，可以使用以下方法。

**1。Atoi()函数:**Atoi 代表 ASCII 到整数，返回 parsent(s，10，0)转换为 Int 类型的结果。

**语法:**

```go
func Atoi(s string) (int, error)
```

**例:**

## 走

```go
// Go program to illustrate how to
// Convert string to the integer type

package main

import (
    "fmt"
    "strconv"
)

func main() {

    str1 := "123"

    // using ParseInt method
    int1, err := strconv.ParseInt(str1, 6, 12)

    fmt.Println(int1)

    // If the input string contains the integer
    // greater than base, get the zero value in return
    str2 := "123"

    int2, err := strconv.ParseInt(str2, 2, 32)
    fmt.Println(int2, err)

}
```