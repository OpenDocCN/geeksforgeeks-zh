# 在 Golang 中转换字符串中布尔类型的不同方法

> 原文：[https://www.geeksforgeeks.org/different-ways-to-convert-the-boolean-type-in-string-in-golang/](https://www.geeksforgeeks.org/different-ways-to-convert-the-boolean-type-in-string-in-golang/)

为了在 Golang 中将 `bool` 类型转换为 `string` 类型，可以使用 `strconv` 和 `fmt` 包功能。

**1. `strconv.FormatBool()` 方法：**
`FormatBool` 用于将布尔类型转换为字符串。它根据 `b` 的值返回 `"true"` 或 `"false"`。

**语法：**
```go
func FormatBool(b bool) string
```

**示例：** 使用 `strconv` 包的 `FormatBool()` 函数将布尔类型转换为字符串。

```go
// Go program to illustrate
// How to convert the
// Boolean Type into String
package main

import (
    "fmt"
    "strconv"
)

//Main Function
func main() {
    i := true
    s := strconv.FormatBool(i)
    fmt.Printf("Type : %T \nValue : %v\n", s, s)
}
```