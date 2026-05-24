# 如何在 Golang 中把字符串转换成大写？

> 原文:[https://www . geesforgeks . org/如何转换大写字母字符串/golang/](https://www.geeksforgeeks.org/how-to-convert-a-string-in-uppercase-in-golang/)

在 Go 语言中，字符串不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go 字符串中，允许使用以下函数将字符串转换为大写。所有这些函数都是在 strings package 下定义的，因此您必须在程序中导入 strings package 才能访问这些函数:

**1。ToUpper:** 此函数用于将给定的字符串元素转换为大写。或者换句话说，该函数返回给定字符串的副本，其中所有 Unicode 字符都被映射为大写。

**语法:**

```go
func ToUpper(str string) string
```

这里， *str* 代表要转换成大写的字符串。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to convert
// the given string into uppercase
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
    str4 := "uppercase conversion"

    // Displaying strings
    fmt.Println("Strings (before):")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)
    fmt.Println("String 3:", str3)
    fmt.Println("String 4:", str4)

    // Converting all the string into uppercase
    // Using ToUpper() function
    res1 := strings.ToUpper(str1)
    res2 := strings.ToUpper(str2)
    res3 := strings.ToUpper(str3)
    res4 := strings.ToUpper(str4)

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
String 4: uppercase conversion

Strings (after):
Result 1:  WELCOME, GEEKSFORGEEKS**
Result 2: $THIS IS THE, TUTORIAL OF GOLANG##
Result 3: HELLO! GOLANG
Result 4: UPPERCASE CONVERSION

```

**2。ToTitle:** 该函数用于将字符串元素转换为标题大小写。或者换句话说，这个函数返回一个给定字符串的副本，其中所有的 Unicode 字符都被映射为标题大小写。

**语法:**

```go
func ToTitle(str string) string
```

这里，*字符串*代表要转换为标题大小写的字符串。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to convert
// the given string into title case
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
    str4 := "uppercase conversion"

    // Displaying strings
    fmt.Println("Strings (before):")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)
    fmt.Println("String 3:", str3)
    fmt.Println("String 4:", str4)

    // Converting all the string into title case
    // Using ToTitle() function
    res1 := strings.ToTitle(str1)
    res2 := strings.ToTitle(str2)
    res3 := strings.ToTitle(str3)
    res4 := strings.ToTitle(str4)

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
String 4: uppercase conversion

Strings (after):
Result 1:  WELCOME, GEEKSFORGEEKS**
Result 2: $THIS IS THE, TUTORIAL OF GOLANG##
Result 3: HELLO! GOLANG
Result 4: UPPERCASE CONVERSION

```