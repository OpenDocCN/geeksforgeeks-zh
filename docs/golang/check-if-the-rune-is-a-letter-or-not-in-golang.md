# 检查符文在戈朗是否为字母

> 原文:[https://www . geeksforgeeks . org/check-如果符文是字母或非字母在 golang/](https://www.geeksforgeeks.org/check-if-the-rune-is-a-letter-or-not-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
可以借助 **IsLetter()** 功能检查给定的符文是不是字母。如果给定的符文是字母，此函数返回 true 如果给定的符文不是字母，则返回 false。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func IsLetter(r rune) bool
```

这个函数的返回类型是布尔型的。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to
// check the given rune is a letter
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
    rune_3 := '1'
    rune_4 := '4'
    rune_5 := 'S'

    // Checking the given rune 
    // is a letter or not
    // Using IsLetter() function
    res_1 := unicode.IsLetter(rune_1)
    res_2 := unicode.IsLetter(rune_2)
    res_3 := unicode.IsLetter(rune_3)
    res_4 := unicode.IsLetter(rune_4)
    res_5 := unicode.IsLetter(rune_5)

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
true
true
false
false
true

```

**例 2:**

```go
// Go program to illustrate how to
// check the given rune is a letter
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating a slice of rune
    val := []rune{'g', 'E', '3', 'K', '1'}

    // Checking each element of the given 
    // slice of the rune is a letter or not
    // Using IsLetter() function
    for i := 0; i < len(val); i++ {

        if unicode.IsLetter(val[i]) == true {

            fmt.Println("It is a letter")

        } else {

            fmt.Println("It is not a letter")
        }
    }
}
```

**输出:**

```go
It is a letter
It is a letter
It is not a letter
It is a letter
It is not a letter

```