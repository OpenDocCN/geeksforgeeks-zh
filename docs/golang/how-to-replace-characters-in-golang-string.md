# 如何替换 Golang 字符串中的字符？

> 原文:[https://www . geesforgeks . org/如何替换 golang-string 中的字符/](https://www.geeksforgeeks.org/how-to-replace-characters-in-golang-string/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go 字符串中，允许使用给定的函数替换给定字符串中的字符。这些函数是在 strings package 下定义的，因此您必须在程序中导入 strings package 才能访问这些函数:

**1。替换:**该函数返回包含新字符串的字符串副本，新字符串是通过替换旧字符串中的元素而创建的。如果给定的旧字符串是空的，那么它在字符串的开始匹配，并且在每个 UTF-8 序列之后，它产生多达 m+1 个 m-符文字符串的替换。如果 n 的值小于零，那么这个函数可以替换给定字符串中的任意数量的元素(没有任何限制)。

**语法:**

```go
func Replace(str, oldstr, newstr string, m int) string
```

这里 *str* 是原弦， *oldstr* 是你要替换的弦， *newstr* 是替换 *oldstr* 的新弦， *n* 是 *oldstr* 替换的次数。

**示例:**

```go
// Go program to illustrate how to
// replace characters in the given string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    str1 := "Welcome to Geeks for Geeks"
    str2 := "This is the article of the Go string is a replacement"

    fmt.Println("Original strings")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)

    // Replacing strings
    // Using Replace() function
    res1 := strings.Replace(str1, "e", "E", 3)
    res2 := strings.Replace(str2, "is", "IS", -2)
    res3 := strings.Replace(str1, "Geeks", "GFG", 0)

    // Displaying the result
    fmt.Println("\nStrings(After replacement)")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Original strings
String 1:  Welcome to Geeks for Geeks
String 2:  This is the article of the Go string is a replacement

Strings(After replacement)
Result 1:  WElcomE to GEeks for Geeks
Result 2:  ThIS IS the article of the Go string IS a replacement
Result 3:  Welcome to Geeks for Geeks

```

**2。ReplaceAll:** 此函数用于用新字符串替换所有旧字符串。如果给定的旧字符串是空的，那么它在字符串的开始匹配，并且在每个 UTF-8 序列之后，它产生多达 M+1 个 M 符文字符串的替换。

**语法:**

```go
func ReplaceAll(str, oldstr, newstr string) string
```

这里 *str* 是原弦， *oldstr* 是你要替换的弦， *newstr* 是替换 *oldstr* 的新弦。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to
// replace characters in the given string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    str1 := "Welcome to Geeks for Geeks"
    str2 := "This is the is the article of the Go string is a replacement"

    fmt.Println("Original strings")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)

    // Replacing strings
    //  Using ReplaceAll() function
    res1 := strings.ReplaceAll(str1, "Geeks", "GFG")
    res2 := strings.ReplaceAll(str2, "the", "THE")

    // Displaying the result
    fmt.Println("\nStrings(After replacement)")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)

}
```

**输出:**

```go
Original strings
String 1:  Welcome to Geeks for Geeks
String 2:  This is the is the article of the Go string is a replacement

Strings(After replacement)
Result 1:  Welcome to GFG for GFG
Result 2:  This is THE is THE article of THE Go string is a replacement

```