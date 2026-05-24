# 如何统计一个 Golang 字符串中重复的字符数？

> 原文:[https://www . geeksforgeeks . org/如何计算字符串中重复字符的数量/](https://www.geeksforgeeks.org/how-to-count-the-number-of-repeated-characters-in-a-golang-string/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go 字符串中，可以借助 *Count()* 功能统计字符串中某些特定的 Unicode 码点或 *costr* (重复字符)的非重叠实例数。此函数返回一个值，该值代表给定字符串或字符串中存在的 Unicode 代码点的总数。它是在字符串包下定义的，所以您必须在程序中导入字符串包来访问计数函数。

**语法:**

```go
func Count(str, costr string) int
```

这里*弦*是原弦 *costr* 是我们要计数的弦。如果 *costr* 的值为空，则该函数返回 1 +字符串中的 Unicode 码点数。

**示例:**

```go
// Go program to illustrate how to
// count the elements of the string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing the strings
    str1 := "Welcome to the online portal of GeeksforGeeks"
    str2 := "My dog name is Dollar"
    str3 := "I like to play Ludo"

    // Displaying strings
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)
    fmt.Println("String 3: ", str3)

    // Counting the elements of the strings
    // Using Count() function
    res1 := strings.Count(str1, "o")
    res2 := strings.Count(str2, "do")

    // Here, it also counts white spaces
    res3 := strings.Count(str3, "")
    res4 := strings.Count("GeeksforGeeks, geeks", "as")

    // Displaying the result
    fmt.Println("\nResult 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)

}
```

**输出:**

```go
String 1:  Welcome to the online portal of GeeksforGeeks
String 2:  My dog name is Dollar
String 3:  I like to play Ludo

Result 1:  6
Result 2:  1
Result 3:  20
Result 4:  0

```