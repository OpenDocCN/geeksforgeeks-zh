# 如何在格朗劈开一根弦？

> 原文:[https://www . geesforgeks . org/如何在 golang 中拆分字符串/](https://www.geeksforgeeks.org/how-to-split-a-string-in-golang/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。在 Go strings 中，您可以在以下函数的帮助下将字符串拆分为一个片段。这些函数是在 strings package 下定义的，因此您必须在程序中导入 strings package 来访问这些函数:

**1。Split:** 这个函数将一个字符串分割成由给定分隔符分隔的所有子字符串，并返回包含这些子字符串的切片。

**语法:**

```go
func Split(str, sep string) []string
```

这里 *str* 是字符串，sep 是分隔符。如果 *str* 不包含给定的 *sep* 和 *sep* 非空，那么它将返回一个长度为 1 的切片，该切片只包含 *str* 。或者如果 *sep* 是空的，那么它将在每个 UTF-8 序列之后分裂。或者如果 *str* 和 *sep* 都为空，则返回空切片。

**示例:**

```go
// Go program to illustrate how to split a string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing the strings
    str1 := "Welcome, to the, online portal, of GeeksforGeeks"
    str2 := "My dog name is Dollar"
    str3 := "I like to play Ludo"

    // Displaying strings
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)
    fmt.Println("String 3: ", str3)

    // Splitting the given strings
    // Using Split() function
    res1 := strings.Split(str1, ",")
    res2 := strings.Split(str2, "")
    res3 := strings.Split(str3, "!")
    res4 := strings.Split("", "GeeksforGeeks, geeks")

    // Displaying the result

    fmt.Println("\nResult 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)

}
```

**输出:**

```go
String 1:  Welcome, to the, online portal, of GeeksforGeeks
String 2:  My dog name is Dollar
String 3:  I like to play Ludo

Result 1:  [Welcome  to the  online portal  of GeeksforGeeks]
Result 2:  [M y   d o g   n a m e   i s   N a w a b]
Result 3:  [I like to play Ludo]
Result 4:  []

```

**2。SplitAfter:** 该函数在给定分隔符的每个实例之后将字符串拆分为所有子字符串，并返回包含这些子字符串的切片。

**语法:**

```go
func SplitAfter(str, sep string) []string
```

这里 *str* 是字符串，sep 是分隔符。如果 *str* 不包含给定的 *sep* 和 *sep* 非空，那么它将返回一个长度为 1 的切片，该切片只包含 *str* 。或者如果 *sep* 是空的，那么它将在每个 UTF-8 序列之后分裂。或者如果 *str* 和 *sep* 都为空，则返回空切片。

**示例:**

```go
// Go program to illustrate how to split a string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing the strings
    str1 := "Welcome, to the, online portal, of GeeksforGeeks"
    str2 := "My dog name is Dollar"
    str3 := "I like to play Ludo"

    // Displaying strings
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)
    fmt.Println("String 3: ", str3)

    // Splitting the given strings
    // Using SplitAfter() function
    res1 := strings.SplitAfter(str1, ",")
    res2 := strings.SplitAfter(str2, "")
    res3 := strings.SplitAfter(str3, "!")
    res4 := strings.SplitAfter("", "GeeksforGeeks, geeks")

    // Displaying the result
    fmt.Println("\nResult 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)

}
```

**输出:**

```go
String 1:  Welcome, to the, online portal, of GeeksforGeeks
String 2:  My dog name is Dollar
String 3:  I like to play Ludo

Result 1:  [Welcome,  to the,  online portal,  of GeeksforGeeks]
Result 2:  [M y   d o g   n a m e   i s   N a w a b]
Result 3:  [I like to play Ludo]
Result 4:  []

```

**3。SplitAfterN:** 该函数在给定分隔符的每个实例之后将一个字符串拆分为所有子字符串，并返回包含这些子字符串的切片。

**语法:**

```go
func SplitAfterN(str, sep string, m int) []string
```

这里， *str* 是字符串， *sep* 是分隔符，m 用来查找要返回的子字符串个数。这里如果 **m > 0** ，那么最多返回 *m* 个子串，最后一个字符串子串不会拆分。如果 **m == 0** ，则返回零。如果 **m < 0** ，则返回所有子串。

**示例:**

```go
// Go program to illustrate how to split a string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing the strings
    str1 := "Welcome, to the, online portal, of GeeksforGeeks"
    str2 := "My dog name is Dollar"
    str3 := "I like to play Ludo"

    // Displaying strings
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)
    fmt.Println("String 3: ", str3)

    // Splitting the given strings
    // Using SplitAfterN() function
    res1 := strings.SplitAfterN(str1, ",", 2)
    res2 := strings.SplitAfterN(str2, "", 4)
    res3 := strings.SplitAfterN(str3, "!", 1)
    res4 := strings.SplitAfterN("", "GeeksforGeeks, geeks", 3)

    // Displaying the result
    fmt.Println("\nResult 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)

}
```

**输出:**

```go
String 1:  Welcome, to the, online portal, of GeeksforGeeks
String 2:  My dog name is Dollar
String 3:  I like to play Ludo

Result 1:  [Welcome,  to the, online portal, of GeeksforGeeks]
Result 2:  [M y   dog name is Dollar]
Result 3:  [I like to play Ludo]
Result 4:  []

```