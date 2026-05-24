# 检查字符串是否以 Golang

中指定的后缀结尾

> 原文:[https://www . geesforgeks . org/check-如果字符串以指定的后缀 in-golang 结尾/](https://www.geeksforgeeks.org/check-if-the-string-ends-with-specified-suffix-in-golang/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go strings 中，可以借助 **HasSuffix()** 功能检查字符串是否以指定后缀结尾。如果给定的字符串以指定的后缀结束，该函数返回 *true* ，如果给定的字符串不以指定的后缀结束，该函数返回 false。它是在字符串包下定义的，所以您必须在程序中导入字符串包才能访问 *HasSuffix* 函数。

**语法:**

```go
func HasSuffix(str, suf string) bool
```

这里 *str* 是原字符串， *suf* 是代表后缀的字符串。此函数的返回类型是 bool 类型。

**示例:**

```go
// Go program to illustrate how to check the
// given string start with the specified prefix
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    // Using shorthand declaration
    s1 := "I am working as a Technical content writer in GeeksforGeeks!"
    s2 := "I am currently writing articles on Go language!"

    // Checking the given strings 
    // starts with the specified prefix
    // Using HasSuffix() function
    res1 := strings.HasSuffix(s1, "GeeksforGeeks!")
    res2 := strings.HasSuffix(s1, "!")
    res3 := strings.HasSuffix(s1, "Apple")
    res4 := strings.HasSuffix(s2, "language!")
    res5 := strings.HasSuffix(s2, "dog")
    res6 := strings.HasSuffix("GeeksforGeeks, Geeks", "Geeks")
    res7 := strings.HasSuffix("Welcome to GeeksforGeeks", "Welcome")

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)
    fmt.Println("Result 5: ", res5)
    fmt.Println("Result 6: ", res6)
    fmt.Println("Result 7: ", res7)
}
```

**输出:**

```go
Result 1:  true
Result 2:  true
Result 3:  false
Result 4:  true
Result 5:  false
Result 6:  true
Result 7:  false

```