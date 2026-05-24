# 在 Golang 中转换字符串中布尔类型的不同方法

> 原文:[https://www . geeksforgeeks . org/golang 中字符串布尔类型的不同转换方式/](https://www.geeksforgeeks.org/different-ways-to-convert-the-boolean-type-in-string-in-golang/)

为了在 Golang 中将**布尔**类型转换为**字符串**类型，可以使用 **strconv 和 fmt** 包功能。

**1。** **strconv。FormatBool()方法:****format bool**用于将布尔类型转换为字符串。它根据 b 的值返回“真”或“假”。

**语法:**

```go
func FormatBool(b bool) string

```

**示例:** C 使用 strconv 将布尔类型转换为字符串。 FormatBool () 功能 。

## 转

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