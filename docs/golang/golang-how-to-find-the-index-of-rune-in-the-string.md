# Golang |如何找到弦中符文的索引？

> 原文:[https://www . geesforgeks . org/golang-如何找到字符串中的符文索引/](https://www.geeksforgeeks.org/golang-how-to-find-the-index-of-rune-in-the-string/)

在 Go 语言中，字符串不同于其他语言，如 Java、C++、Python 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go 字符串中，也可以使用 **IndexRune()** 函数找到给定字符串中指定符文的第一个索引。此函数返回 Unicode 代码点的第一个实例的索引，即指定的符文，如果指定的符文不在给定的字符串中，则返回-1。如果符文是 *utf8。符文错误*，然后它返回任何无效的 UTF 8 字节序列的第一个实例。它是在字符串包下定义的，所以你必须在你的程序中导入字符串包来访问索引函数。

**语法:**

```go
func IndexRune(str string, r rune) int
```

**例 1:**

```go
// Go program to illustrate how to find
// the index value of the given rune
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Creating and Finding the first index 
    // of the rune in the given string
    // Using IndexRunefunction
    res1 := strings.IndexRune("****Welcome to GeeksforGeeks****", 60)

    res2 := strings.IndexRune("Learning how to trim"+
                           " a slice of bytes", 'r')

    res3 := strings.IndexRune("GeeksforGeeks", 'G')

    // Display the results
    fmt.Println("Index Value 1: ", res1)
    fmt.Println("Index Value 2: ", res2)
    fmt.Println("Index Value 3: ", res3)

}
```

**输出:**

```go
Index Value 1:  -1
Index Value 2:  3
Index Value 3:  0

```

**例 2:**

```go
// Go program to illustrate how to find
// the index value of the given rune
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Creating and initializing a string
    // Using shorthand declaration
    string_1 := "Welcome to GeeksforGeeks"
    string_2 := "AppleAppleAppleAppleAppleApple"
    string_3 := "%G%E%E%K%S"

    // Creating and initializing rune
    var r1, r2, r3 rune
    r1 = 'R'
    r2 = 'l'
    r3 = 42

    // Finding the first index
    // of the given rune
    // Using IndexRune function
    res1 := strings.IndexRune(string_1, r1)
    res2 := strings.IndexRune(string_2, r2)
    res3 := strings.IndexRune(string_3, r3)

    // Display the results
    fmt.Printf("String 1: %s , Rune 1:%q , Index Value: %d",
                                         string_1, r1, res1)

    fmt.Printf("\nString 2: %s , Rune 2:%q , Index Value: %d",
                                           string_2, r2, res2)

    fmt.Printf("\nString 3: %s , Rune 3:%q , Index Value: %d", 
                                           string_3, r3, res3)

}
```

**输出:**

```go
String 1: Welcome to GeeksforGeeks , Rune 1:'R' , Index Value: -1
String 2: AppleAppleAppleAppleAppleApple , Rune 2:'l' , Index Value: 3
String 3: %G%E%E%K%S , Rune 3:'*' , Index Value: -1

```