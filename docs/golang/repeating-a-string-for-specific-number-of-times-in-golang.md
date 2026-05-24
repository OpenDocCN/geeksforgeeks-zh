# 在 Golang 中重复特定次数的字符串

> 原文:[https://www . geesforgeks . org/repeating-a-string-for-specific-次数-in-golang/](https://www.geeksforgeeks.org/repeating-a-string-for-specific-number-of-times-in-golang/)

在 Go 语言中，[字符串](https://www.geeksforgeeks.org/strings-in-golang/)不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。
借助**重复()**功能，您可以重复特定次数的字符串。这个方法返回一个包含重复字符串的新字符串，它是在 strings 包下定义的。因此，您必须在程序中导入字符串包来访问 Repeat 函数。

**语法:**

```go
func Repeat(str string, count int) string
```

这里， *str* 代表你要重复的字符串，计数值代表你要重复 str string 的次数。

**例 1:**

```go
// Go program to illustrate how to repeat
// a string to a specific number of times
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing a string
    // Using shorthand declaration
    str1 := "Welcome to GeeksforGeeks !.."
    str2 := "This is the tutorial of Go"

    // Repeating the given strings
    // Using Repeat function
    res1 := strings.Repeat(str1, 4)
    res2 := str2 + strings.Repeat("Language..", 2)

    // Display the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
}
```

**输出:**

> 结果 1:欢迎来到极客论坛！..欢迎来到极客乐园！..欢迎来到极客乐园！..欢迎来到极客乐园！..
> 结果 2:这是 GoLanguage 的教程..语言..

**注意:**如果 count 的值为负或者(len(str) * count)的结果溢出，则此方法会死机。

**示例:**

```go
// Go program to illustrate how to repeat
// a string to a specific number of times
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing a string
    // Using shorthand declaration
    str1 := "Welcome to GeeksforGeeks !.."
    str2 := "This is the tutorial of Go"

    // Repeating the given strings
    // Using Repeat function
    res1 := strings.Repeat(str1, 4)

    // If we use a negative value in the count
    // then this method will panic because negative
    // values are not allowed to count
    res2 := str2 + strings.Repeat("Language..", -2)

    // Display the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
}
```

**输出:**

> 恐慌:字符串:负重复计数
> 
> goro tine 1[running]:
> 字符串。重复(0x104b22，0xa，0xfffffffe，0x0，0x450000，0x 70)
> /usr/local/go/src/strings/strings . go:533+0x 540
> main . main()
> /tmp/sandbox 829702598/Prog . go:25+0x 80