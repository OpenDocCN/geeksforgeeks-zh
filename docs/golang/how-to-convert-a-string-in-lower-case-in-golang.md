# 如何在 Golang 中转换小写字符串？

> 原文:[https://www . geesforgeks . org/如何转换小写字母字符串/golang/](https://www.geeksforgeeks.org/how-to-convert-a-string-in-lower-case-in-golang/)

在 Go 语言中，字符串不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go string 中，允许使用 **ToLower()** 函数转换小写字符串。此函数返回给定字符串的副本，其中所有 Unicode 字母都映射为小写。这个函数是在 strings package 下定义的，所以你必须在程序中导入 strings package 才能访问这个函数。

**语法:**

```go
func ToLower(str string) string
```

在这里，*字符串*代表要转换成小写的字符串。

**示例:**

```go
// Go program to illustrate how to convert
// the given string to lowercase
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    str1 := "WelcomE, GeeksforGeeks**"
    str2 := "$This is the, tuTorial oF Golang##"
    str3 := "HELLO! GOLANG"
    str4 := "lowercase conversion"

    // Displaying strings
    fmt.Println("Strings (before):")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)
    fmt.Println("String 3:", str3)
    fmt.Println("String 4:", str4)

    // Converting all the string into lowercase
    // Using ToLower() function
    res1 := strings.ToLower(str1)
    res2 := strings.ToLower(str2)
    res3 := strings.ToLower(str3)
    res4 := strings.ToLower(str4)

    // Displaying the results
    fmt.Println("\nStrings (after):")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
    fmt.Println("Result 3:", res3)
    fmt.Println("Result 4:", res4)
}
```

**输出:**

```go
Strings (before):
String 1:  WelcomE, GeeksforGeeks**
String 2: $This is the, tuTorial oF Golang##
String 3: HELLO! GOLANG
String 4: lowercase conversion

Strings (after):
Result 1:  welcome, geeksforgeeks**
Result 2: $this is the, tutorial of golang##
Result 3: hello! golang
Result 4: lowercase conversion

```