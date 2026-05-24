# 如何在 Golang 中的 Unicode 大小写折叠下检查 String 是否相等？

> 原文:[https://www . geeksforgeeks . org/如何在 unicode 下检查字符串是否相等-大小写折叠在 golang/](https://www.geeksforgeeks.org/how-to-check-string-for-equality-under-unicode-case-folding-in-golang/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go strings 中，借助 *EqualFold()* 功能，即使两个字符串写在不同的情况下(小写和大写)，也可以毫无错误地相互比较。或者换句话说，该函数用于检查指定的字符串是否被解释为 UTF-8 字符串，并且在 Unicode 大小写折叠下是否相等。如果给定字符串在 Unicode 大小写折叠下相等，则此函数返回 true 如果给定字符串在 Unicode 大小写折叠下不相等，则返回 false。它是在字符串包下定义的，因此您必须在程序中导入字符串包才能访问 EqualFold 功能。

**语法:**

```go
func EqualFold(str1, str2 string) bool
```

此函数的返回类型是 bool 类型。让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to
// check the given strings are equal or not
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating strings
    // Using var keyword
    var username string
    var uinput string

    // Initializing strings
    username = "AnkitaSaini"
    uinput = "ankitasaINI"

    // Checking whether the given
    // strings are equal or not
    // Using EqualFold() function
    res := strings.EqualFold(username, uinput)

    // Displaying the result according
    // to the given condition
    if res == true {

        fmt.Println("!..Successfully Matched..!")
    } else {

        fmt.Println("!..Not Matched..!")
    }

}
```

**输出:**

```go
!..Successfully Matched..!
```

**例 2:**

```go
// Go program to illustrate how to check
// the given strings are equal or not
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    // Using shorthand declaration
    s1 := "I am working as a Technical content writer, in GeeksforGeeks!"
    s2 := "I am currently writing articles on Go language!"

    // Checking the given strings are equal or not
    // Using EqualFold() function
    res1 := strings.EqualFold(s1, "I AM WORKING AS A TECHNICAL CONTENT WRITER, IN GEEKSFORGEEKS!")
    res2 := strings.EqualFold(s1, "I AM working AS A Technical CONTENT writer, IN GeeksforGeeks!")
    res3 := strings.EqualFold(s1, "Apple")
    res4 := strings.EqualFold(s2, "I am currently writing articles on Go language!")
    res5 := strings.EqualFold(s2, "I am currently writing ARTICLES on Go language!")
    res6 := strings.EqualFold("GeeksforGeeks", "geeksForgeeks")

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
Result 2:  true
Result 3:  false
Result 4:  true
Result 5:  true
Result 6:  true

```