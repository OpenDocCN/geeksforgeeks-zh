# 检查给定字符是否出现在 Golang 字符串中

> 原文:[https://www . geesforgeks . org/check-if-the-given-characters-in-golang-string/](https://www.geeksforgeeks.org/check-if-the-given-characters-is-present-in-golang-string/)

在 Go 语言中，[字符串](http://geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。在 Go 字符串中，您可以使用给定的函数检查字符串中的给定字符。这些函数是在 strings package 下定义的，因此您必须在程序中导入 strings package 才能访问这些函数:

**1。包含:**该函数用于检查给定字符串中是否存在给定的字母。如果给定字符串中有字母，则返回 true，否则返回 false。

**语法:**

```go
func Contains(str, chstr string) bool
```

这里*字符串*是原字符串， *chstr* 是你要检查的字符串。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check
// the string is present or not in the
// specified string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    str1 := "Welcome to Geeks for Geeks"
    str2 := "Here! we learn about go strings"

    fmt.Println("Original strings")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)

    // Checking the string present or not
    //  Using Contains() function
    res1 := strings.Contains(str1, "Geeks")
    res2 := strings.Contains(str2, "GFG")

    // Displaying the result
    fmt.Println("\nResult 1: ", res1)
    fmt.Println("Result 2: ", res2)

}
```

**输出:**

```go
Original strings
String 1:  Welcome to Geeks for Geeks
String 2:  Here! we learn about go strings

Result 1:  true
Result 2:  false

```

**2。ContainsAny:** 此函数用于检查给定字符串中是否存在字符中的任何 Unicode 代码点。如果在给定的字符串中可以使用字符中的任何 Unicode 代码点，则此方法返回 true，否则返回 false。

**语法:**

```go
func ContainsAny(str, charstr string) bool
```

这里， *str* 是原始字符串， *charstr* 是字符中的 Unicode 码位。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check the
// string is present or not in the specified
// string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    str1 := "Welcome to Geeks for Geeks"
    str2 := "Here! we learn about go strings"

    // Checking the string present or not
    // Using ContainsAny() function
    res1 := strings.ContainsAny(str1, "Geeks")
    res2 := strings.ContainsAny(str2, "GFG")
    res3 := strings.ContainsAny("GeeksforGeeks", "G & f")
    res4 := strings.ContainsAny("GeeksforGeeks", "u | e")
    res5 := strings.ContainsAny(" ", " ")
    res6 := strings.ContainsAny("GeeksforGeeks", " ")

    // Displaying the result
    fmt.Println("\nResult 1: ", res1)
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
Result 4:  true
Result 5:  true
Result 6:  false

```