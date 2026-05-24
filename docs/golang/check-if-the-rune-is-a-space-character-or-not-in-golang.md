# 检查符文是否为空符

> 原文:[https://www . geesforgeks . org/check-如果符文是空格字符或不在 golang/](https://www.geeksforgeeks.org/check-if-the-rune-is-a-space-character-or-not-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
在 **IsSymbol()** 函数的帮助下，你可以检查给定的符文是否是空格字符或者不是由 Unicode 的 White Space 属性定义的。如果给定的符文是空格字符，此函数返回 true 如果给定的符文不是空格字符，则返回 false。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func IsSpace(r rune) bool
```

这个函数的返回类型是布尔型的。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to check
// the given rune is a space character
// or not
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating rune
    rune_1 := 'g'
    rune_2 := 'e'
    rune_3 := '\t'
    rune_4 := '\n'
    rune_5 := 'S'

    // Checking the given rune is
    // a space character or not
    // Using IsSpace () function
    res_1 := unicode.IsSpace(rune_1)
    res_2 := unicode.IsSpace(rune_2)
    res_3 := unicode.IsSpace(rune_3)
    res_4 := unicode.IsSpace(rune_4)
    res_5 := unicode.IsSpace(rune_5)

    // Displaying results
    fmt.Println(res_1)
    fmt.Println(res_2)
    fmt.Println(res_3)
    fmt.Println(res_4)
    fmt.Println(res_5)

}
```

**输出:**

```go
false
false
true
true
false

```

**例 2:**

```go
// Go program to illustrate how to check
// the given rune is a space character
// or not
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating a slice of rune
    val := []rune{'g', '\f', '\v', '&', ' '}

    // Checking the given rune is
    // a space character or not
    // Using IsSpace () function
    for i := 0; i < len(val); i++ {

        if unicode.IsSpace(val[i]) == true {

            fmt.Println("It is a space character")

        } else {

            fmt.Println("It is not a space character")
        }
    }
}
```

**输出:**

```go
It is not a space character
It is a space character
It is a space character
It is not a space character
It is a space character

```