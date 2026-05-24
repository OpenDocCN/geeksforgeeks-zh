# Golang |在指定分隔符后拆分字符串

> 原文:[https://www . geesforgeks . org/golang-在指定分隔符后拆分字符串/](https://www.geeksforgeeks.org/golang-splitting-the-string-after-the-specified-separator/)

在 Go 语言中，字符串不同于其他语言，如 Java、C++、Python 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go 字符串中，您可以使用 **SplitN()** 函数在指定的分隔符后拆分字符串。此函数在给定分隔符的每个实例之后将一个片段拆分为所有子字符串，并返回这些分隔符之间的子字符串片段。计数表示要返回的子策略的数量。它是在字符串包下定义的，所以您必须在程序中导入字符串包才能访问 SplitN 函数。

**语法:**

```go
func SplitN(str, sep string, m int) []string
```

这里**字符串**是字符串， **sep** 是分隔符。如果 *str* 不包含给定的 *sep* 和 *sep* 非空，那么它将返回一个长度为 1 的切片，该切片只包含 *str* 。或者如果 *sep* 是空的，那么它将在每个 UTF-8 序列之后分裂。或者如果 *str* 和 *sep* 都为空，则返回一个空切片。

**例 1:**

```go
// Go program to illustrate the concept
// of splitting a string
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Creating and Splitting a string
    // Using SplitN function
    res1 := strings.SplitN("****Welcome, to, GeeksforGeeks****", ",", -1)

    res2 := strings.SplitN("Learning x how x to x trim"+
                       " x a x slice of bytes", "x", 3)

    res3 := strings.SplitN("Geeks,for,Geeks, Geek", ",", 0)

    res4 := strings.SplitN("", ",", 2)

    // Display the results
    fmt.Printf("\nFinal Result after splitting:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)
    fmt.Printf("\nSlice 4: %s", res4)
}
```

**输出:**

```go
Final Result after splitting:

Slice 1: [****Welcome  to  GeeksforGeeks****]
Slice 2: [Learning   how   to x trim x a x slice of bytes]
Slice 3: []
Slice 4: []

```

**例 2:**

```go
// Go program to illustrate the concept
// of splitting the string
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Creating and initializing a string
    // Using shorthand declaration
    string_1 := "Welcome, to, Geeks, for, Geeks"
    string_2 := "AppleAppleAppleAppleAppleApple"
    string_3 := "%G%E%E%K%sS"

    // Displaying strings
    fmt.Println("Original Strings:")
    fmt.Printf("String 1: %s", string_1)
    fmt.Printf("\nString 2: %s", string_2)
    fmt.Printf("\nString 3: %s", string_3)

    // Splitting the given strings
    // Using SplitN function
    res1 := strings.SplitN(string_1, ",", 2)
    res2 := strings.SplitN(string_2, "pp", 3)
    res3 := strings.SplitN(string_3, "%", 0)

    // Display the results
    fmt.Printf("\n\nAfter splitting:\n")
    fmt.Printf("\nString 1: %s", res1)
    fmt.Printf("\nString 2: %s", res2)
    fmt.Printf("\nString 3: %s", res3)

}
```

**输出:**

```go
Original Strings:
String 1: Welcome, to, Geeks, for, Geeks
String 2: AppleAppleAppleAppleAppleApple
String 3: %G%E%E%K%sS

After splitting:

String 1: [Welcome  to, Geeks, for, Geeks]
String 2: [A leA leAppleAppleAppleApple]
String 3: []

```