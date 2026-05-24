# 如何在 Golang 中找到指定字符串的最后一个索引值？

> 原文:[https://www . geesforgeks . org/如何在 golang 中找到指定字符串的最后一个索引值/](https://www.geeksforgeeks.org/how-to-find-the-last-index-value-of-specified-string-in-golang/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go strings 中，可以使用以下函数从原始字符串中找到指定字符串的最后一个索引值。这些函数是在 strings package 下定义的，因此您必须在程序中导入 strings package 来访问这些函数:

**1。LastIndex:** 此函数用于从原始字符串中查找给定字符串的最后一个实例的索引值。如果给定的字符串在原始字符串中不可用，则此方法将返回-1。

**语法:**

```go
func LastIndex(str, sbstr string) int
```

这里 *str* 是原始字符串， *sbstr* 是一个字符串，我们要找到它的最后一个索引值。

**示例:**

```go
// Go program to illustrate how to find
// the last index value of the given string
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

    // Finding the last index value of the given string
    // Using LastIndex() function
    res1 := strings.LastIndex(str1, "e")
    res2 := strings.LastIndex(str2, "do")
    res3 := strings.LastIndex(str3, "jk")
    res4 := strings.LastIndex("GeeksforGeeks, geeks", "ks")

    // Displaying the result
    fmt.Println("\nIndex values:")
    fmt.Println("Result 1: ", res1)
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

Index values:
Result 1:  42
Result 2:  3
Result 3:  -1
Result 4:  18

```

**2。LastIndexAny:** 此方法从原始字符串中的字符返回任何 Unicode 代码点的最后一个实例的索引。如果字符的 Unicode 代码点在原始字符串中不可用，则此方法将返回-1。

**语法:**

```go
func LastIndexAny(str, charstr string) int
```

这里， *str* 是原始字符串， *charstr* 是一个 Unicode 代码点，我们想从它的字符中找到最后一个索引值。

**示例:**

```go
// Go program to illustrate how to find the
// last index value of the given string
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

    // Finding the last index value of the given string
    // Using LastIndexAny() function
    res1 := strings.LastIndexAny(str1, "mewdv")
    res2 := strings.LastIndexAny(str2, "ll")
    res3 := strings.LastIndexAny(str3, "qzmj")
    res4 := strings.LastIndexAny("GeeksforGeeks, geeks", "ee")

    // Displaying the result
    fmt.Println("\nIndex values:")
    fmt.Println("Result 1: ", res1)
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

Index values:
Result 1:  42
Result 2:  18
Result 3:  -1
Result 4:  17

```

**3。LastIndexByte:** 该函数返回原始字符串中给定字节的最后一个实例的索引。如果给定的字节在原始字符串中不可用，则此方法将返回-1。

**语法:**

```go
func LastIndexByte(str string, b byte) int
```

这里， *str* 是原始字符串， *b* 是一个字节，我们要找到它的最后一个索引值。

**示例:**

```go
// Go program to illustrate how to find the
// last index value of the given bytes
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

    // Finding the last index value of the given bytes
    // Using LastIndexByte() function
    res1 := strings.LastIndexByte(str1, 'e')
    res2 := strings.LastIndexByte(str2, 'a')
    res3 := strings.LastIndexByte(str3, 'q')
    res4 := strings.LastIndexByte("GeeksforGeeks, geeks", 's')

    // Displaying the result
    fmt.Println("\nIndex values:")
    fmt.Println("Result 1: ", res1)
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

Index values:
Result 1:  42
Result 2:  19
Result 3:  -1
Result 4:  19

```