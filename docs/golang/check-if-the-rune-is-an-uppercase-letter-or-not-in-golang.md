# 检查符文在 Golang 中是否是大写字母

> 原文:[https://www . geesforgeks . org/check-如果符文是大写字母或不在 golang/](https://www.geeksforgeeks.org/check-if-the-rune-is-an-uppercase-letter-or-not-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
可以借助 **IsUpper()** 功能检查给定符文是否为大写字母。如果给定的符文是大写字母，此函数返回 true 如果给定的符文不是大写字母，则返回 false。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func IsUpper(r rune) bool
```

这个函数的返回类型是布尔型的。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to check
// the given rune is an uppercase letter
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
    rune_3 := 'E'
    rune_4 := 'k'
    rune_5 := 'S'

    // Checking the given rune is
    // an upper case letter or not
    // Using IsUpper() function
    res_1 := unicode.IsUpper(rune_1)
    res_2 := unicode.IsUpper(rune_2)
    res_3 := unicode.IsUpper(rune_3)
    res_4 := unicode.IsUpper(rune_4)
    res_5 := unicode.IsUpper(rune_5)

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
false
true

```

**例 2:**

```go
// Go program to illustrate how to check
// the given rune is an Uppercase letter
// or not
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating a slice of rune
    val := []rune{'g', 'E', 'e', 'K', 's'}

    // Checking each element of the given
    // slice of the rune is an uppercase 
    // letter or not
    // Using IsUpper() function
    for i := 0; i < len(val); i++ {

        if unicode.IsUpper(val[i]) == true {

            fmt.Printf("\n%c is an uppercase letter", val[i])

        } else {

            fmt.Printf("\n%c is not an uppercase letter", val[i])
        }
    }
}
```

**输出:**

```go
g is not an uppercase letter
E is an uppercase letter
e is not an uppercase letter
K is an uppercase letter
s is not an uppercase letter

```