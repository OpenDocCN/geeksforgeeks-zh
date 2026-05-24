# 如何查看戈朗弦中指定的符文？

> 原文:[https://www . geesforgeks . org/如何检查指定的符文字符串/](https://www.geeksforgeeks.org/how-to-check-the-specified-rune-in-golang-string/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
在 Go 字符串中，您可以使用 **ContainsRune()** 功能检查给定的字符串中是否包含指定的符文。如果给定的字符串包含指定的符文，该函数返回 true 如果给定的字符串不包含指定的符文，该函数返回 false。它是在字符串包下定义的，所以你必须在你的程序中导入字符串包来访问 ContainsRune 函数。

**语法:**

```go
func ContainsRune(str string, r rune) bool
```

这里*弦*是弦， *r* 是 s 符文。这个函数的返回类型是 bool。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to check
// the given string containing the rune
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
    r2 = 'p'
    r3 = 42

    // Check the given string 
    // containing the rune
    // Using ContainsRune function
    res1 := strings.ContainsRune(string_1, r1)
    res2 := strings.ContainsRune(string_2, r2)
    res3 := strings.ContainsRune(string_3, r3)

    // Display the results
    fmt.Printf("String 1: %s , Rune 1: %q , Present or Not: %t",
                                             string_1, r1, res1)

    fmt.Printf("\nString 2: %s , Rune 2: %q , Present or Not: %t",
                                               string_2, r2, res2)

    fmt.Printf("\nString 3: %s , Rune 3: %q , Present or Not: %t",
                                               string_3, r3, res3)

}
```

**输出:**

```go
String 1: Welcome to GeeksforGeeks , Rune 1: 'R' , Present or Not: false
String 2: AppleAppleAppleAppleAppleApple , Rune 2: 'p' , Present or Not: true
String 3: %G%E%E%K%S , Rune 3: '*' , Present or Not: false

```

**例 2:**

```go
// Go program to illustrate how to check
// the given string containing the rune
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Creating and Checking the given 
    // rune present in the given string
    // Using ContainsRune function
    res1 := strings.ContainsRune("****Welcome, to,"+
                           " GeeksforGeeks****", 60)

    res2 := strings.ContainsRune("Learning x how x to "+
                     "x trim x a x slice of bytes", 'r')

    res3 := strings.ContainsRune("Geeks,for,Geeks, Geek", 'G')

    // Display the results
    fmt.Println("Final Result:")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)

}
```

**输出:**

```go
Final Result:
Result 1:  false
Result 2:  true
Result 3:  true

```