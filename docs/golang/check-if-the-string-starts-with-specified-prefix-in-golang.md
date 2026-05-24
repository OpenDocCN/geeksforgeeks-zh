# 检查字符串是否以 Golang

中指定的前缀开头

> 原文:[https://www . geesforgeks . org/check-if-the-string-start-if-specified-prefix-in-golang/](https://www.geeksforgeeks.org/check-if-the-string-starts-with-specified-prefix-in-golang/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Golang 字符串中，可以借助 **HasPrefix()** 功能检查字符串是否以指定前缀开头。如果给定字符串以指定前缀开头，则该函数返回 true 如果给定字符串不以指定前缀开头，则返回 false。它是在字符串包下定义的，所以您必须在程序中导入字符串包来访问 HasPrefix 函数。

**语法:**

```go
func HasPrefix(str, pre string) bool
```

这里， *str* 是原始字符串，pre 是代表前缀的字符串。此函数的返回类型是 bool 类型。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check
// the given string starts with the
// specified prefix
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

    // Checking the given strings starts with the specified prefix
    // Using HasPrefix() function
    res1 := strings.HasPrefix(s1, "I")
    res2 := strings.HasPrefix(s1, "My")
    res3 := strings.HasPrefix(s2, "I")
    res4 := strings.HasPrefix(s2, "We")
    res5 := strings.HasPrefix("GeeksforGeeks", "Welcome")
    res6 := strings.HasPrefix("Welcome to GeeksforGeeks", "Welcome")

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)
    fmt.Println("Result 5: ", res5)
    fmt.Println("Result 6: ", res6)
}
```

**输出:**

```go
Result 1:  true
Result 2:  false
Result 3:  true
Result 4:  false
Result 5:  false
Result 6:  true

```